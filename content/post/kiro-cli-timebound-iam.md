---
title: 'Getting Kiro CLI to use short lived AWS credentials'
date: '2026-02-19'
tags : [ kiro, timebound-iam, agentic ai, security  ]
canonicalUrl: "https://dev.to/aws/getting-kiro-cli-to-use-short-lived-aws-credentials-55d2"
---

Agentic AI tools like Kiro IDE and Kiro CLI are pretty awesome. You provide the right context, the right prompt, and away they will go. After a period of time, you can now review the output.

Early on developers understood the power, but also the potential harm that could be cause (and we began to read stories like [this one](https://www.theregister.com/2025/07/21/replit_saastr_vibe_coding_incident/). Most developer tools now provide capabilities that allow you as a developer to have fine grain control of what they can and more importantly, should never do. (If you want details, you can check out my hands on workshop on Kiro CLI where I dive deep into these capabilities [here](https://www.theregister.com/2025/07/21/replit_saastr_vibe_coding_incident/))

> As an aside, if the tool you are using does not provide these controls, you should seriously look at re-evaluating the tools and find the one that works best for you!

## timebound-iam

This week I discovered a new tool that can help you provide further controls on what your agentic AI tools can do, specifically when it comes to providing controls about how to limit access to your AWS resources.

**[timebound-iam](https://timebound-iam.com/)** is an mcp server that allows you to vend short term credentials to access your AWS resources. It is pretty simple in concept.

1. You define a role and permissions policy that you associate with your agentic AI tool (in my case I am using Kiro CLI)
2. You install the timebound-iam tool in your machine
3. You configure your agentic-AI tool to use this tool via MCP integration
4. You add steering/rules files to enforce using timebound-iam tools when access your AWS resources

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/rjqkgmeg6b5688m91g6o.png)

## Setting up my AWS permissions

The first thing I needed to do was to setup a new role and IAM policy that would be used to vend short lived credentials. I like this approach as it allows you to take an AWS approach to fine grain control over what resources you might want your agentic AI tools to have access to.

The tool provides help in this respect, providing a walk through of what you need to create. Type:

```
timebound-iam setup aws
```

And it will ask you for which services you want to control access to, and then helps you with what you need to create. I follow these instructions, and for the purposes of testing, I create a new role called "timebound-iam-broker", and generating an inline policy that looked like the following.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "s3:GetObject",
                "s3:ListBucket"
            ],
            "Resource": [
                "arn:aws:s3:::094459-assets",
                "arn:aws:s3:::094459-assets/*"
            ]
        }
    ]
}
```

This was deliberately narrow as I wanted to test how Kiro would handle this (and how hard it would try and work around any blocks that it encountered).

## Configuring this in Kiro CLI

To get this up and running in Kiro CLI, after I installed the timebound-iam tool (using brew install builder-magic/tap/timebound-iam), I created a new custom agent in Kiro. Here is my configuration.

```
{
  "name": "timebound",
  "description": "",
  "prompt": null,
  "mcpServers": {
    "timebound-iam": {
      "autoApprove": [],
      "disabled": false,
      "command": "/opt/homebrew/bin/timebound-iam",
      "args": [
        "serve"
      ]
    }
  },
  "tools": [
    "*"
  ],
  "toolAliases": {},
  "allowedTools": [],
  "resources": [
	"file://AGENTS.md"],
  "hooks": {},
  "toolsSettings": {},
  "includeMcpJson": true,
  "model": null
}
```

I then created a file in the root of my project workspace called AGENTS.md, and added these directives.

```
**When accessing AWS resources**

- ALWAYS use the timebound-iam mcp server to access AWS resources
- use the grant_access tool to vend short lived credentials
- NEVER use standard AWS credentials for accessing AWS resources, EVEN when you get Access Denied errors using timebound-iam
```

> I was undecided about whether this was the best approach. I had initially thought about defining the custom agent with this as its system prompt. I might try again in the future to see if it makes any difference.

I then started my Kiro-CLI session using this custom agent. I could see that the mcp server had started successfully,

```
Model: auto (/model to change) | Plan: KIRO POWER (/usage for more detail)

Checkpoints are not available in this directory. Use '/checkpoint init' to enable checkpoints.

✓ timebound-iam loaded in 0.04 s

[timebound] > /mcp

timebound-iam
▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔
[2026:12:23]: ✓ timebound-iam loaded in 0.04 s
```

and that I had new tools available to me.

```
timebound-iam (MCP)
- grant_access                180    not trusted
- list_active_sessions         40    not trusted
- list_services                50    not trusted
```

I next trusted these tools using the "/tools trust {tool name}" command:

```
[timebound] > /tools trust grant_access


Tool '@timebound-iam/grant_access' is now trusted. I will not ask for confirmation before running this tool.
```

And that was it. I was now ready to test this out.

## Testing timebound-iam

From the Kiro CLI prompt, I tried to do the following operations:

- view files from the allowed S3 bucket
- write files from the allowed S3 bucket
- view files from other S3 buckets
- get general info on my EC2 instances

**Viewing files**

This is the output I got from my Kiro CLI session:

```
[timebound] > list files in my s3 bucket 094459-assets

> I'll help you list the files in your S3 bucket. First, I need to get temporary credentials to access S3.
Running tool grant_access with the param (from mcp server: timebound-iam)
 ⋮  {
 ⋮    "services": [
 ⋮      "s3"
 ⋮    ],
 ⋮    "level": "read_only",
 ⋮    "ttl": "15m"
 ⋮  }

I will run the following command: env $(cat /var/folders/sn/h2yml_6n46vcq93q4c9qrzqh0000gr/T/timebound-iam-2968778292/timebound-iam-c3160a49-0aaf-4b6b-b96f-2d6428f46b26.env) aws s3 ls s3://094459-assets/ (using tool: shell)
Purpose: List files in S3 bucket 094459-assets


Allow this action? Use 't' to trust (always allow) this tool for the session. [y/n/t]:

[timebound] > t

                           PRE uploads/
2023-03-29 09:15:39       2199 about.html
<redacted>

 - Completed in 1.179s

The bucket contains 26 files plus the uploads/ directory.

 ▸ Credits: 0.14 • Time: 22s
```

So this worked as expected. I could see that Kiro used this tool (grant_access) to generated short lived credentials, and then executed. You can see that it generates these credentials in temp files (/var/folders/sn/h2yml_6n46vcq93q4c9qrzqh0000gr/T/timebound-iam-2968778292/timebound-iam-c3160a49-0aaf-4b6b-b96f-2d6428f46b26.env) which all look as you would expect

```
AWS_ACCESS_KEY_ID=ASIA2ICLXOKDCSHLV4AL
AWS_SECRET_ACCESS_KEY=XNDncGZ4HoPL8X8DtaJQSJtgfGrZkQ0QunlRVET4
AWS_SESSION_TOKEN=IQo<redacted>==
```

**Don't panic!** those credentials are short lived, if you try and use them you will get "An error occurred (ExpiredToken) when calling the ListBuckets operation: The provided token has expired."

We can use one of the tools to see the currently available (live) sessions.

```
[timebound] > can you list active sessions in timebound-iam

Running tool list_active_sessions with the param (from mcp server: timebound-iam)
 ⋮  {}

> You have 1 active timebound-iam sessions:

1. Session ID: timebound-iam-c3160a49-0aaf-4b6b-b96f-2d6428f46b26
   - Services: s3
   - Level: read_only
   - Expires: 2026-02-19T11:26:56Z (11m 24s remaining)

 ▸ Credits: 0.07 • Time: 9s
```

**Writing files**

Ok so what happens if we try and ask Kiro to write a file into this directory.

```
[timebound] > write a file called "audit.test" in the same bucket

> I'll create a file called "audit.test" in your S3 bucket. First, I need to get write access credentials.

Running tool grant_access with the param (from mcp server: timebound-iam)
 ⋮  {
 ⋮    "level": "full",
 ⋮    "services": [
 ⋮      "s3"
 ⋮    ],
 ⋮    "ttl": "15m"
 ⋮  }
 - Completed in 0.39s

I will run the following command: echo "test" | env $(cat /var/folders/sn/h2yml_6n46vcq93q4c9qrzqh0000gr/T/timebound-iam-2968778292/timebound-iam-7428f4f3-46b0-4bb9-abc7-7f979aa583e7.env) aws s3 cp - s3://094459-assets/audit.test (using tool: shell)
Purpose: Upload audit.test file to S3 bucket

upload failed: - to s3://094459-assets/audit.test An error occurred (AccessDenied) when calling the PutObject operation: User: arn:aws:sts::704533066374:assumed-role/timebound-iam-broker/timebound-iam-7428f4f3-46b0-4bb9-abc7-7f979aa583e7 is not authorized to perform: s3:PutObject on resource: "arn:aws:s3:::094459-assets/audit.test" because no identity-based policy allows the s3:PutObject action
 - Completed in 1.0s

> I received an Access Denied error. The timebound-iam credentials don't have permission to write to this bucket. This could be due to:

1. The bucket policy or IAM role restrictions
2. The timebound-iam broker role doesn't have PutObject permissions for this bucket

You may need to check the bucket permissions or the timebound-iam configuration to allow write access to the 094459-assets bucket.

 ▸ Credits: 0.12 • Time: 13s
```

As expected this failed. The permissions assigned to the timebound-iam-broker role does not permit write operations.

The key thing here is that IF YOU DO NOT HAVE A RULES file, then your agentic AI will try alternative approaches. Remember, I still have my  standard federated credentials in my "~/.aws" directory, and so when I tried this WITHOUT the rules defined in the AGENTS.md file, Kiro just switched to using those credentials.

Rules are important and help you control the behaviour of your agentic AI tools.

**Accessing EC2 resources**

I get similar results when trying to access other AWS resources not defined within my timebound-iam-broker policy.

```
[timebound] > ok can you tell me about my ec2 instances in eu-west-1 please

> I'll get temporary credentials for EC2 and check your instances in eu-west-1.

Running tool grant_access with the param (from mcp server: timebound-iam)
 ⋮  {
 ⋮    "level": "read_only",
 ⋮    "services": [
 ⋮      "ec2"
 ⋮    ],
 ⋮    "ttl": "15m"
 ⋮  }
 - Completed in 0.153s

I will run the following command: env $(cat /var/folders/sn/h2yml_6n46vcq93q4c9qrzqh0000gr/T/timebound-iam-2968778292/timebound-iam-e2bc8a5a-23b8-4396-81fa-05c930d847ab.env) aws ec2 describe-instances --region eu-west-1 --query 'Reservations[*].Instances[*].[InstanceId,InstanceType,State.Name,PublicIpAddress,PrivateIpAddress,Tags[?Key==`Name`].Value|[0]]' --output table (using tool: shell)
Purpose: List EC2 instances in eu-west-1

An error occurred (UnauthorizedOperation) when calling the DescribeInstances operation: You are not authorized to perform this operation. User: arn:aws:sts::704533066374:assumed-role/timebound-iam-broker/timebound-iam-e2bc8a5a-23b8-4396-81fa-05c930d847ab is not authorized to perform: ec2:DescribeInstances because no identity-based policy allows the ec2:DescribeInstances action
 - Completed in 1.118s

> I'm getting an Access Denied error. The timebound-iam-broker role doesn't have permission to perform ec2:DescribeInstances.

Similar to the S3 write issue earlier, the timebound-iam system can create sessions for EC2, but the underlying broker role lacks the necessary EC2 permissions to actually describe instances.

The timebound-iam-broker role would need ec2:DescribeInstances permission added to its IAM policy to allow
querying EC2 instances.

 ▸ Credits: 0.13 • Time: 12s
```

**Viewing other S3 buckets**

As expected, even though its a READ only operation, I get blocked when trying to list all available S3 buckets.

```
[timebound] > can you list all available s3 buckets

> I'll get S3 credentials and list all your buckets.
Running tool grant_access with the param (from mcp server: timebound-iam)
 ⋮  {
 ⋮    "level": "read_only",
 ⋮    "services": [
 ⋮      "s3"
 ⋮    ],
 ⋮    "ttl": "15m"
 ⋮  }
 - Completed in 1.152s

I will run the following command: env $(cat /var/folders/sn/h2yml_6n46vcq93q4c9qrzqh0000gr/T/timebound-iam-2968778292/timebound-iam-b7bec1f2-a215-4d3d-aa6d-e420aa7ec698.env) aws s3 ls (using tool: shell)
Purpose: List all S3 buckets

An error occurred (AccessDenied) when calling the ListBuckets operation: User: arn:aws:sts::704533066374:assumed-role/timebound-iam-broker/timebound-iam-b7bec1f2-a215-4d3d-aa6d-e420aa7ec698 is not authorized to perform: s3:ListAllMyBuckets because no identity-based policy allows the s3:ListAllMyBuckets action
 - Completed in 2.216s

> The timebound-iam-broker role doesn't have permission to list all S3 buckets. It lacks the s3:ListAllMyBuckets permission.

Earlier I was able to list files within the specific bucket 094459-assets because the broker role has permissions for bucket-level operations, but not the account-level operation to list all buckets.

To enable this, the broker role would need this permission added:

json
{
  "Effect": "Allow",
  "Action": "s3:ListAllMyBuckets",
  "Resource": "*"
}


 ▸ Credits: 0.18 • Time: 19s
```

I do appreciate though how Kiro is trying to help me here!


**What do I think?**

I have been testing this tool over the last few days to get a grip of how it works. It is a great start, although if you decided to evaluate this yourself, here are some things to think about.

1. You still need to have AWS credentials available when using this tool. When you start the "broker" (the timebound-iam server) it will use these to vend temporary credentials that will then be used.

2. You have to define a rules file to enforce this. If you do not do this, then agentic AI is going to do what agentic AI does best - work around any errors (permissions or expired credentials).

3. I need to battle test this more as I have only spent a few days with it configured in my main custom agent. I will update this post if I discover anything, but in the meantime, if you decide to evaluate make sure that you take the usual precautions (i.e. do not let this anywhere near stuff you care about, e.g. production!) 

If you like the project, make sure you give feedback to [Rahul Singh](https://x.com/arrsingh) and star/follow the project.

### Get started today

You can get started with Kiro CLI today for free. [Download it from this link](https://kiro.dev/downloads/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el).  I have created a workshop if you are new to Kiro CLI and the [Kiro CLI workshop](https://github.com/094459/aqd-cli-workshop) will walk you through getting started with the terminal based Kiro CLI tool, and provides a comprehensive overview as well as advanced topics.

Made with ♥ from DevRel