---
title: 'Using aws-vault to manage access to your AWS resources from Kiro CLI'
date: '2026-02-019'
tags : [ kiro, agentic ai, security, aws-vault  ]
canonicalUrl: "https://dev.to/aws/using-aws-vault-to-manage-access-to-your-aws-resources-from-kiro-cli-29ab"
---

As we say at AWS, security is our top priority. This is why I have been spending time thinking about how to manage what our agentic AI tools can do. After publishing a previous post on this topic ([Getting Kiro CLI to use short lived AWS credentials](https://dev.to/aws/getting-kiro-cli-to-use-short-lived-aws-credentials-55d2)), this post takes a look at another approach you can take. [Vincent](https://www.linkedin.com/in/vincentds/) reminded me about an awesome open source tool called [aws-vault](https://github.com/ByteNess/aws-vault) that helps developers move to using short lived, temporary credentials. In this post I wanted to compare and contrast approaches. But first, let me walk you through the setup.

> The documentation for aws-vault is good, and it has pretty much everything you need. That said, I did want to include in this post how I configured it to work with AWS Identity Centre, which is what I use.

**Setting things up**

Like timebound-iam, aws-vault is a tool that needs to be installed. Installation is painless, a quick "brew install aws-vault" and I was good to go.

Also like timebound-iam, you need to associate aws-vault with credentials. aws-vault provides a lot of flexibility with regards to how it will work with your existing credentials (go check the [usage](https://github.com/ByteNess/aws-vault/blob/main/USAGE.md) guide for info). 

In my particular setup, as I use AWS Identity Centre, this is what I did to get aws-vault working for me.

* From the IdC console, I created a new permissions set that I would associated with aws-vault. This entails either using existing managed IAM policies or creating your own. I decided to use a managed ReadOnly policy that provides me with only read access to my AWS environment (I called this KiroCLIView)
* From the IdC console, I assigned this to an existing user and my AWS account
* I then created a new sso profile in my local "~/.aws/config" that looks like this (where {aws_account_no} is my AWS account number):

```
[profile KiroCLIView]
sso_start_url=https://beachgeek-uk.awsapps.com/start
sso_account_id = {aws_account_no}
sso_role_name = KiroCLIView
sso_region = eu-west-1
region = eu-west-1
```

That is all I had to do. To test it, I used the following command:

```
aws-vault exec KiroCLIView -- aws s3 ls
```

After first asking me to provide a password to my keystore, a new browser window is opened, and I then follow my typical Idc login flow (user credentials and MFA token). I only have to do this the first time, subsequent logins are simplified.


```
Opening the SSO authorization page in your default browser (use Ctrl-C to abort)
https://beachgeek-uk.awsapps.com/start/#/device?user_code=FJBS-GWZH
```

After entering my details, I now see a list of my buckets on S3.

Like timebound-aim, aws-vault provides tools to help you manage your sessions. I can view all existing sessions using "aws-vault list"

```
Profile                  Credentials              Sessions
=======                ===========           ========
KiroCLIView          -                        		sso.GetRoleCredentials:11h57m52s
-                        		-                        		oidc:https://beachgeek-uk.awsapps.com/start
```

I can also clear any sessions using is the "aws-vault clear" (you will be asked to authenticate when you do this).

**Configuring Kiro**

On the Kiro side, the setup is simpler - no MCP server. All I do is create a new custom agent with a rule file that asks it to always use aws-vault when accessing AWS resources. This is what it looks like:

```
**When accessing AWS resources**

- ALWAYS use aws-vault to login to AWS when you need to access AWS resources
- To get credentials, you will have to use "aws-vault exec KiroCLIView" to initially get access to AWS credentials
```

and here is my custom agent config file

```
{
  "name": "vault",
  "description": "",
  "prompt": null,
  "mcpServers": {
  },
  "tools": [
    "*"
  ],
  "toolAliases": {},
  "allowedTools": [],
  "resources": [
	"file://AGENTS.md"],
  "hooks": {},
  "toolsSettings": {}
}
```

From within my Kiro CLI session, when I now ask it to interact with AWS, I can see that Kiro CLI is ensuring that aws-vault is used to generate these temporary credentials.

```
[vault] >

tell me what is in my s3 bucket 094459-assets

> I'll list the contents of your S3 bucket 094459-assets using aws-vault for credentials.
I will run the following command: aws-vault exec KiroCLIView -- aws s3 ls s3://094459-assets/ (using tool: shell)
Purpose: List contents of S3 bucket 094459-assets using aws-vault

Opening the SSO authorization page in your default browser (use Ctrl-C to abort)
https://beachgeek-uk.awsapps.com/start/#/device?user_code=QFRZ-VPWL

<redacted>

Files:
- HTML files: about.html, index.html
- JavaScript libraries: linkify-html.js, linkify.js, qrcode.js
- Images: favicon.ico, presign-arch.png, several JPEG files
- Video files: Multiple large MP4 files (OSS news episodes 165-174, ranging from ~186MB to ~305MB)
- Log file: audit.log (47 bytes, updated today)

The bucket has a mix of web assets, video content, and some presigned URL test files based on the naming
patterns.

 ▸ Credits: 0.08 • Time: 34s
```

If I ask it to write a file into this bucket

```
[vault] > can you write a file called audit.test into that bucket

> I'll create a file called audit.test and upload it to your S3 bucket.
I will run the following command: echo "test" > /tmp/audit.test && aws-vault exec KiroCLIView -- aws s3 cp /tmp/audit.test s3://094459-assets/audit.test (using tool: shell)
Purpose: Create audit.test file and upload to S3 bucket

upload failed: ../../../../tmp/audit.test to s3://094459-assets/audit.test An error occurred (AccessDenied) when calling the PutObject operation: User: arn:aws:sts::704533066374:assumed-role/AWSReservedSSO_KiroCLIView_c3c565557df10f4f/ricsue@amazon.co.uk is not authorized to perform: s3:PutObject on resource: "arn:aws:s3:::094459-assets/audit.test" because no identity-based policy allows the s3:PutObject action
 - Completed in 1.431s

> I can't upload the file because your current AWS role (KiroCLIView) doesn't have s3:PutObject
permissions on this bucket. The role only has read access.

You'll need to either:
- Use a different AWS profile/role with write permissions to this bucket
- Have an administrator grant s3:PutObject permission to your current role

 ▸ Credits: 0.06 • Time: 8s
```

It works as expected.

If I open up a new terminal, and use my normal credentials which does have write access, I can successfully write the file.

```
>~/kiro-cli/aws-vault  aws s3 cp AGENTS.md s3://094459-assets
upload: ./AGENTS.md to s3://094459-assets/AGENTS.md

 >~/kiro-cli/aws-vault  aws s3 ls 094459-assets
                           PRE uploads/
2026-02-19 17:46:43        226 AGENTS.md
```

If I logout of that session and then try and access my AWS resources, I get the usual error

```
Unable to locate credentials. You can configure credentials by running "aws login".
```

This is a little more flexible than timebound-iam, which requires you to have an active AWS session to work.

The final thing I wanted to try is to configure the duration of the temporary credentials. timebound-iam has a 15 min session timeout, but I noticed that the credentials aws-vault were using were set to 60 minutes. It turns out that you can configure most of the characteristics of your session by using environment variables (great docs make a big difference).

By setting "AWS_SESSION_TOKEN_TTL=15m" in my rules file, I was able to tune those temporary credentials down from the default. Nice.

**Which one should you use?**

In these two posts I have looked at a couple of ways you can manage access to your AWS resources from your agentic AI tools. I guess the question some of you might be asking is which one should I use?

They both perform similar tasks, and have similar requirements to get them up and running. That said, there are a couple of things that are nudging me towards aws-vault over timebound-iam. First is maturity. timebound-iam is a new tool and so its just getting started. I am sure it will develop and mature over time, but it lacks the features and capabilities that have evolved in aws-vault over the years. The second reason is that timebound-iam requires you to have a valid AWS session before it will generated short lived credentials, something that you do not need with aws-vault. This feels cleaner and it also mitigates the scenario where the agent might try and work around the rules files you create. The final reason is simplicity - timebound-iam is an MCP server which requires that additional configuration, whereas aws-vault is just something you define in your rules file.

In this short video you can see aws-vault in action.

{{< youtube Y0b3srfln9E >}}

**What's next?**

The last two posts have looked at just one aspect of how you can manage access to downstream systems that your agentic AI tools are using. Whilst in these examples I have used my AWS account and resources, it is likely that you will be access a much broader range of systems. You should start to think about what tools exist that will allow you to manage control to those systems. 

This has got me thinking about creating something more comprehensive. Across the different layers, how can we optimise for control and security. Watch this space, as I will be noodling and coming up with some thoughts on this in the coming weeks.

### Get started today

You can get started with Kiro CLI today for free. [Download it from this link](https://kiro.dev/downloads/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el).  I have created a workshop if you are new to Kiro CLI and the [Kiro CLI workshop](https://github.com/094459/aqd-cli-workshop) will walk you through getting started with the terminal based Kiro CLI tool, and provides a comprehensive overview as well as advanced topics.

Finally, if you did find this post interesting, helpful, or useful, I would love to get your feedback. Please [use this 30 second feedback form](https://pulse.aws/survey/OZ7QIXA7) and I will be forever grateful.

Made with ♥ from DevRel