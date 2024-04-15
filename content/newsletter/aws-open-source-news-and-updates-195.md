---
title: 'AWS open source newsletter #195'
date: '2024-04-15'
tags : [ oss-newsletter, aws open source, bref, Valkey, Remix, AWS Amplify, Kubernetes, Amazon EKS, Apache Airflow, MWAA, Cedar, LangChain, AWS CDK, LangServe, Lean, Itsio, Cilium, Amazon Linux 2023, PyTorch, OpenEBS, PostgreSQL, MySQL, Apache Iceberg, Apache Griffin, Amazon EMR, OpenSearch, Ruby, Karpenter, Argo]
canonicalUrl: "https://community.aws/content/2ea38u0x4DZ91l6BO2CoWHPo7rw/aws-open-source-newsletter-195"
---

##  Edition #195

Welcome to issue #195 of the AWS open source newsletter, the newsletter where we try and provide you the best open source on AWS content. This week I am heading out to Everything Open, and looking forward to meeting the community in Gladstone. I will be talking about Cedar, and showing why it is important and how it works (demo is working lovely now). I am now on the third week of my open source roadshow, which is why I have had to change the publishing of this newsletter to every other week - at least until I get back home.

As always, in this edition we feature lots of great new projects, including a number of projects from the AWS Community Builders. We have projects that integrate with generative AI to make your developer life easier, we have a Python library that extends some of the limits when working with Amazon SQS, a nice work in progress tool to simplify working with Amazon DynamoDB, a visualiser for your Terraform plans, a starter project for bref, a serverless CMS solution, as well as the usual selection of demo projects (which of course feature how to get started with generative AI).

We also have content featuring a broad range of open source projects, which this week includes Valkey, Remix, AWS Amplify, Kubernetes, Apache Airflow, Cedar, LangChain, AWS CDK, LangServe, Lean, Itsio, Cilium, Amazon Linux 2023, PyTorch, OpenEBS, PostgreSQL, MySQL, Apache Iceberg, Apache Griffin, Amazon EMR, OpenSearch, Ruby, Karpenter, and Argo.

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution. The projects mentioned here do not represent any formal recommendation or endorsement, I am just sharing for greater awareness as I think they look useful and interesting!*

### Tools

**gh-relfind**

[gh-relfind](https://aws-oss.beachgeek.co.uk/3tf) is a project from AWS Community Builder Colin Duggan, that provides a simple Go CLI tool that uses Claude to parse package changes from GitHub repos release history. Significant change information is often contained in the release text field (body tag in the JSON response from ListReleases). Adding a semantic search makes it easier to extract and summarise actual change details. The project was built to get a better understanding of how to integrate with Claude through AWS Bedrock. Very neat indeed!

**safeaws-cli**

[safeaws-cli](https://aws-oss.beachgeek.co.uk/3te) is a project from AWS Community Builder Gabriel Koo that provides an AWS CLI wrapper that helps you avoid common mistakes and pitfalls with Amazon Bedrock's Large Language Models, checking your command arguments against the command docs. safeaws-cli empowers you to execute AWS commands confidently by leveraging Amazon Bedrock's AI language models to analyze CLI commands, fetch help text, and identify potential issues or concerns before execution. By providing a safety net that mitigates pitfalls, safeaws-cli allows users to explore AWS securely, fostering a more informed approach to working with the CLI.

Check out Gabriel's post, [`safeaws` checks your AWS CLI commands before they are run](https://aws-oss.beachgeek.co.uk/3tl), for more details including a short demo video of this in action.

![demo of safeaws in action](https://github.com/gabrielkoo/safeaws-cli/blob/main/demo.gif?raw=true)

**amazon-sqs-python-extended-client-lib**

[amazon-sqs-python-extended-client-lib](https://aws-oss.beachgeek.co.uk/3ti) this repo (Amazon SQS Extended Client) allows clients to manage Amazon SQS message payloads that exceed the 256 KB message size limit, up to a size of 2 GB. In the event of publishing such large messages, the client accomplishes this feat by storing the actual payload in a S3 bucket and by storing the reference of the stored object in the SQS queue. Similarly, the extended-client is also used for retrieving and dereferencing these references of message objects stored in S3.  Check out the docs for more details on how this works and some sample code to get you going.

**tsynamo**

[tsynamo](https://aws-oss.beachgeek.co.uk/3td) is a project from that Olli Warro that simplifies the DynamoDB API so that you don't have to write commands with raw expressions and hassle with the attribute names and values. Moreover, Tsynamo makes sure you use correct types in your DynamoDB expressions, and the queries are nicer to write with autocompletion. Olli was inspired by another project ([Kysely](https://aws-oss.beachgeek.co.uk/3tm)), and so built this project so that he could do similar using Amazon DynamoDB. He says:

> Instead of calling it type-safe, I decided to go with type-friendly, because the library is still in an early stage, and is not 100% type-safe. Under the hood, Tsynamo compiles the built queries into AWS SDK v3 commands. I feel that Tsynamo simplifies the AWS SDK API quite a lot since the developer doesn't have to mess around with condition/filter expressions or attribute names/values themselves, and as a bonus gets autocompletion for building the queries!

There's also a playground to test it out in your browser (link in the README). Since the project is still in its early stages, it doesn't yet have 100% support for all DynamoDB features, like querying indexes. Olli would love to get some feedback, so if you are interested and find this useful, get in touch with him.

![demo of tysamo](https://github.com/woltsu/tsynamo/blob/5fb5bb349887f0b8f0c903cbba93feb2a4a1ae50/assets/demo.gif?raw=true)

**inkdrop-visualizer**

[inkdrop-visualizer](https://aws-oss.beachgeek.co.uk/3tc) is a handy project from Antoine Descamps, that is still in the very early and looking for feedback from developers, and more specifically those of you using Terraform. Antoine told me that he thinks this tool can help with onboarding engineers, reviewing terraform plans and generating IaC documentation. Antoine is keen to get input from the community to make sure we're building the right features, so if you are a Terraform user on AWS, why not check this out.

![overview of inkdrop](https://github.com/inkdrop-org/inkdrop-visualizer/assets/86591160/5de99a85-2636-40c8-b82d-7f64c7dc7178)

**sigv4a-signing-examples**

[sigv4a-signing-examples](https://aws-oss.beachgeek.co.uk/1jl) provides a useful set of examples that show examples of sigv4 implementations. Josh Hart, maintainer of this repo, has put together a companion repo that has a set of sigv4 examples in different frameworks and using the sdk or from scratch. Josh is also looking for community contributions in other frameworks, so if you are working on a framework and want to combine efforts, drop Josh a note.

**pagemosaic-cms**

[pagemosaic-cms](https://aws-oss.beachgeek.co.uk/3tb) is an open-source platform optimized for AWS to efficiently host static websites. It simplifies the process of creating, managing, and publishing content online with an emphasis on cost-effectiveness and efficient use of AWS resources. You can check out the project home page for more details [here](https://aws-oss.beachgeek.co.uk/3tk).

**symfony-bref-starter**

[symfony-bref-starter](https://aws-oss.beachgeek.co.uk/3ta) is a starter kit for symfony projects using bref / serverless to allow easy deployments. bref is a fantastic and well tested way of running PHP applications via serverless, handling easy deployments and environments on AWS. Check out the README for some very cool stats around bref usage. The repo provides good examples and everything you need to get started.

### Demos, Samples, Solutions and Workshops

**domain-specific-genai-chatbot-with-serverless**

[domain-specific-genai-chatbot-with-serverless](https://aws-oss.beachgeek.co.uk/3t9) This sample demonstrates how to build a domain specific chatbot using serverless and Bedrock. The chatbot employs Retrieval-Augments Generation (RAG) and chat history to provide context for the LLM to answer.

**generate-s3-accelerate-presigned-url**

[generate-s3-accelerate-presigned-url](https://aws-oss.beachgeek.co.uk/3tg) this sample project demonstrates how to generate an Amazon S3 pre-signed URL with S3 Transfer Acceleration, using Amazon API Gateway REST API and AWS Lambda function. The Lambda function, composed in Java 21, is responsible for generating a presigned URL to allow customers to upload a single file into S3, with S3 Transfer Acceleration enabled, to speed up content transfers to Amazon S3 securely, over long distances. The API is protected by IAM authentication, to protect against non-authenticated users.

**amazon-eks-running-webassembly**

[amazon-eks-running-webassembly](https://aws-oss.beachgeek.co.uk/3th) This repository contains code for building custom Amazon EKS AMIs using HashiCorp Packer. The AMIs include necessary binaries and configurations to enable you to run WebAssembly workloads in an EKS cluster and are based on Amazon Linux 2023. The runtimes used in the AMIs are Spin and WasmEdge. The respective containerd-shims are used for both runtimes. Deploying the cluster is done using Hashicorp Terraform. After the cluster is created, RuntimeClasses and example workloads are deployed to the cluster. If you are exploring Wasm, then this is for you.

**genai-sports-commentary**

[genai-sports-commentary](https://aws-oss.beachgeek.co.uk/3tj) is a repo that appeals to my inner spots fan, and looks at how you can apply generative AI and large language models, to create highly personalized contents for sport fans. In our example, we'll use a foundation model to generate play by play commentary based on American Football game data synthetically created (in reality, the data could be directly sourced from the stadiums, or cloud). We'll instruct the model to generate variety of commentary using different prompts. For instance, create prompts to the model to generate commentary in particular commentary writing style, or a particular language that the fans would prefer.

![gif demo of this repo in action](https://github.com/aws-samples/genai-sports-commentary/blob/main/img/genai-sports-commentary-demo.gif?raw=true)

### AWS and Community blog posts
 
Each week I spent a lot of time reading posts from across the AWS community on open source topics. In this section I share what personally caught my eye and interest, and  I hope that many of you will also find them interesting. 

**The best from around the Community**

We start this week on the topic of server side rendering (SSR), and more specifically how to deploy AWS Amplify applications you develop with SSR. AWS Community Builder Rich Buggy has put together this short post, on how you can do this with Remix. Check out his post over at [How to deploy Remix apps with SSR to AWS Amplify](https://aws-oss.beachgeek.co.uk/3t3). Up next is AWS Hero Elliott Cordo covering one of my favourite topics, Apache Airflow, and in the post [MWAA Plugins and Dependency Survival Guide ](https://aws-oss.beachgeek.co.uk/3t4), Elliot provides essential reading for anyone using Managed Workflows for Apache Airflow (MWAA), providing some top topics to help you keep on top of managing your workflows. Cedar is an open source project I have been spending a lot of time with, and I am always very happy to learn more from others who create code or posts. So was super happy when I saw [Validating Cedar policies with GitHub Actions](https://aws-oss.beachgeek.co.uk/3t5), from Chris Norman, that walks you through one way you can treat authorisation as code, and how treating your authorisation policies as source code means you can test and review changes using your existing tools like GitHub Actions or CodeCatalyst. This one is a must read folk, and really shows you the potential of what you can do with this.

AWS Community Builder Dakota Lewallen is back with another CDK post, this time looking at how you can make your architecture more flexible by re-using your existing resources in the post, [To Build or to Reuse? A CDK Question](https://aws-oss.beachgeek.co.uk/3t6). João Galego shows you how to deploy LangChain applications with LangServe in minutes on Amazon ECS and AWS Fargate using AWS Copilot, in his post [Deploy LangChain 🦜🔗 applications on AWS with LangServe 🦜️🏓](https://aws-oss.beachgeek.co.uk/3t7) (yup, gratuitous use of emojis too!). Wrapping things up this week is AWS Community Builder Saifeddine Rajhi, with [Improve your EKS cluster with Istio and Cilium : Better networking and security](https://aws-oss.beachgeek.co.uk/3t8)

**Valkey**

The big news recently was that Redis was moving to a proprietary licence, leaving open source developers asking themselves what do we do? Well the answer was delivered swiftly from a core of the Redis community, who came out with an open source fork, which is called Valkey and part of the Linux Foundation. To find out more, you should read my colleague's post, [Why AWS Supports Valkey](https://aws-oss.beachgeek.co.uk/3su), where Kyle explores this announcement in more detail and includes details as to why AWS is supporting this community fork.

**Lean**

Kesha Hietala and Emina Torlak have put together [Lean Into Verified Software Development](https://aws-oss.beachgeek.co.uk/3sw) that looks at how AWS used Lean in building Cedar in order to satisfy key safety and security properties. This is really cool stuff, as it is one thing to develop security tooling like Cedar, but it isa completely whole new ball game to apply the techniques outlined in this post, in order to help customers have confidence in using them. This weeks essential read.

![overview of the LEAN process](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2024/04/04/proof-of-design-diagram.png)

 **Cloud Native round up**

* [Amazon EKS-Optimized Amazon Linux 2023 AMIs Now Available](https://aws-oss.beachgeek.co.uk/3sp) walks you through the new Amazon Linux 2023 AMIs that you can now use with your kubernetes clusters, including things you should be aware of
* [Scale LLMs with PyTorch 2.0 FSDP on Amazon EKS – Part 2](https://aws-oss.beachgeek.co.uk/3sq) provides a detailed walk through of the PyTorch Fully Sharded Data Parallel (FSDP) library, showing you how it can help you train larger models more efficiently [hands on]

![A figure that shows how FSDP works for two data parallel processes](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2024/03/21/fsdp.png)

* [Adding Storage using OpenEBS on EKS Anywhere](https://aws-oss.beachgeek.co.uk/3sx) shows you how OpenEBS can leverage the existing storage on nodes in an EKS Anywhere cluster to provide persistence support for the workloads [hands on]
* [How Snap Inc. secures its services with Amazon EKS](https://aws-oss.beachgeek.co.uk/3sy) explores Snap’s cloud infrastructure, showing how it has evolved from running a monolith inside Google App Engine, to micro-services deployed in Kubernetes across AWS and GCP
* [Announcing Amazon CloudWatch Container Insights for Amazon EKS Windows Workloads Monitoring](https://aws-oss.beachgeek.co.uk/3sz) walks you through the process of enabling Container Insights for your Amazon EKS Windows cluster [hands on]

![examples cloudwatch dashboard for your eks windows cluster](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2024/04/04/Screenshot-2024-02-13-at-10.30.45%E2%80%AFPM.png)

**Other posts and quick reads**

* [Replicate data between partitioned and non-partitioned tables using trigger functions in Amazon RDS for PostgreSQL or Amazon Aurora PostgreSQL](https://aws-oss.beachgeek.co.uk/3so) shows you how to replicate data between partitioned and non-partitioned tables using trigger functions [hands on]
* [Achieve faster switchover for Amazon RDS Blue/Green Deployments with large number of connections](https://aws-oss.beachgeek.co.uk/3sr) looks at some of the improvements you can see which will reduce overall down time during your Blue/Green MySQL deployments [hands on]
* [Use Apache Iceberg in your data lake with Amazon S3, AWS Glue, and Snowflake](https://aws-oss.beachgeek.co.uk/3ss) explores a couple of architecture patterns for implementing Apache Iceberg in a data lake for better interoperability across AWS and Snowflake

![Architecture diagram that provides a high-level overview of this pattern](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2024/04/03/BDB-4247-image001.png)

* [Automate large-scale data validation using Amazon EMR and Apache Griffin](https://aws-oss.beachgeek.co.uk/3st) is a step-by-step process to validate large datasets using Amazon EMR and Apache Griffin, and open source library for data quality that supports both batch and streaming mode [hands on]

![Data validation framework overview](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2024/03/29/bdb3070_data_validation_1.png)

### Quick updates

**Amazon EMR**

Two updates for you this week.

The first is for those of you running Amazon EMR on Kubernetes, with news that Amazon EMR on EKS has simplified the authentication and authorisation user experience by integrating with Amazon EKS's improved cluster access management controls. With this launch, Amazon EMR on EKS will use EKS access management controls to automatically obtain the necessary permissions to run Amazon EMR applications on the EKS cluster. Amazon EMR on EKS already supports IAM authentication and authorisation to EKS clusters. Before, customers had to configure aws-auth and RBAC (Role-Based Access Control) settings to grant EMR on EKS access to the EKS cluster. Now, by granting the EKS cluster access permissions to the EMR’s IAM role, EMR on EKS will automatically get access to the EKS cluster without any manual RBAC or aws-auth configuration.

For those running Amazon EMR on EC2 instances, you will be happy for this next update, where we have introduced a new Amazon EMR on EC2 feature that enables automatic graceful replacement of unhealthy core nodes to ensure continued optimal cluster operations and prevent data loss. Additionally, EMR on EC2 will publish CloudWatch events to provide visibility into node health and recovery actions. These improvements are available for all Amazon EMR releases. With EMR on EC2, you can easily provision and scale your data processing clusters without having to manage compute infrastructure or open-source application setup. However, there can be circumstances when an EMR node turns unhealthy due to underlying hardware or memory over-utilisation issue. Previously, for termination protected clusters, unhealthy core nodes would remain idle and continue to count towards cluster capacity. For other clusters, the core node replacement process was not graceful. With today’s launch, Amazon EMR minimises job interruption and prevents data loss by gracefully decommissioning and replacing unhealthy core nodes regardless of your cluster’s termination protection setting. Amazon EMR will also publish unhealthy node replacement events that will be available in the EMR console and Amazon EventBridge.

**MySQL**

Amazon Relational Database Service (Amazon RDS) for MySQL now supports rds_superuser_role to simplify implementation of role-based privileges on MySQL 8.0. The rds_superuser_role is granted by default to the primary administrative user, and has privileges including, CREATE ROLE, CREATE USER, and DROP ROLE, for all database objects. For a complete list of rds_superuser_role privileges, refer to the Amazon RDS User Guide. The rds_superuser_role is supported on RDS for MySQL versions 8.0.36 and higher. If you are running a minor version lower than MySQL 8.0.36, you can leverage automatic minor version upgrades to automatically upgrade your databases to more recent minor versions during scheduled maintenance windows. You can also leverage Amazon RDS Blue/Green deployments to perform a major or minor version upgrade with minimal downtime.

**OpenSearch**

A couple of quick updates this week.

Amazon OpenSearch Service is now extending the ability to update the number of data nodes without requiring a blue/green deployment for clusters without dedicated cluster manager (master) nodes. This change will allow you to make node count changes faster. Clusters with dedicated cluster manager nodes already supported updating the data node count without a blue/green deployment. Previously, when you updated the data nodes instance count on your domain without dedicated cluster manager, OpenSearch Service used a blue/green deployment mechanism to make the change. While blue/green deployments are meant to avoid any disruption to your clusters, as the deployment utilises additional resources on the domain, it is recommended that you perform them during low traffic periods. Now, you can update number of data nodes without requiring a blue/green deployment, ensuring that these updates can complete faster, while avoiding any potential disruption to your cluster operations. In cases wherein you modify both data node instance type and count, OpenSearch Service will still use a blue/green deployment. You can use the dry-run option to check whether your change requires a blue/green deployment. The improved experience is available for domains running any OpenSearch version, and Elasticsearch versions 7.1 and above supported on the service.

Following that is news that Amazon OpenSearch Ingestion now enables you to enrich events with geographical location data from an IP address, allowing you to add additional context to your observability and security data in realtime. Additionally, you can configure mapping templates in Amazon OpenSearch clusters to automatically display these enriched events on a geographical map using OpenSearch Dashboards. Amazon OpenSearch Ingestion automatically keeps the mapping of IP addresses to geographical locations up-to- date, allowing you to confidently draw valuable insights for use cases like customer analytics and network access patterns across geographies. Also as part of this launch, Amazon OpenSearch Ingestion now supports Data Prepper 2.7.0 which introduces new features like XML and Amazon Ion data format processors, decompress gzip-compressed fields, truncate processor, codec support for the file source, split_event processor for splitting events and select_entries processor for filtering fields from an event. 

Check out David Venable and George Chen's post on this, [Announcing Data Prepper 2.7.0](https://aws-oss.beachgeek.co.uk/3sm)

**Kubernetes**

Starting with Amazon VPC CNI version 1.18.0, you can now leverage tag-based subnet discovery capability of Amazon VPC CNI to scale Amazon Elastic Kubernetes Service (EKS) clusters in IPv4 address space without adding operational complexity. In this new default mode, Kubernetes Pod IP addresses are allocated from all tagged and available subnets in your Amazon Virtual Private Cloud(VPC). Modernising your applications using Amazon EKS, you are likely looking for ways to optimise IPv4 address space consumption and maximise usage of your VPC CIDRs as well as subnets provisioned for the EKS Pods. Now, Amazon VPC CNI based automatic subnet discovery for Pod IP assignment helps you streamline your network configuration by dynamically allocating IP addresses within defined subnets. You can tag subnets and integrate them seamlessly into an existing EKS cluster networking configuration. Once tagged, Amazon VPC CNI will automatically discover the new VPC subnets with available IP address space and use them to allocate IP addresses for Kubernetes Pods in an EKS cluster.

Srinivas Jasti and Ashok Srirama have put together this post, [Amazon VPC CNI introduces Enhanced Subnet Discovery](https://aws-oss.beachgeek.co.uk/3sv), if you want to dive deeper into this.

Also announced last week was news that Amazon EKS now offers extended support for Kubernetes versions. You can run EKS clusters using any Kubernetes version for up to 26 months from the time the version becomes available on EKS. Extended support for Kubernetes versions is available for Kubernetes versions 1.21 and higher. For a full list of versions and support dates, see here. Standard support begins when a Kubernetes minor version becomes available in EKS, and continues for 14 months - the same as the Kubernetes project support window for minor versions. Past this point, the Kubernetes project stops releasing security patches for a minor version. Extended support in Amazon EKS begins immediately at the end of standard support and continues for 12 months. EKS clusters in extended support will continue to get security patches for the Kubernetes control plane as well as critical patches for the Amazon VPC CNI, kube-proxy, and CoreDNS add-ons, AWS-published EKS-Optimized AMIs, and EKS Fargate nodes. Check out the documentation page for more details, [Amazon EKS Kubernetes versions](https://aws-oss.beachgeek.co.uk/3sn)

**Ruby**

AWS Lambda now supports creating serverless applications using Ruby 3.3. Developers can use Ruby 3.3 as both a managed runtime and a container base image, and AWS will automatically apply updates to the managed runtime and base image as they become available. The Lambda Ruby 3.3 runtime is built on the new Amazon Linux 2023 runtime, which is based on the AL2023 minimal container image. This provides a significantly smaller deployment footprint than earlier Amazon Linux 2-based runtimes, updated versions of common libraries such as glibc, and a new package manager. The Ruby 3.3 runtime also provides access to the latest Ruby language features.

### Videos of the week

**Harnessing Karpenter: Transforming Kubernetes Clusters with Argo Workflows**

Carlos Santana and Raj Saha show you how to seamlessly migrate your Kubernetes resources. While Cluster Autoscaler remains widely used among Kubernetes enthusiasts, this session introduces a groundbreaking approach to transitioning your worker nodes and pods to Karpenter with ease and efficiency, capitalising on Argo Workflows' flexibility and its unique capability to execute CI pipelines within the cluster.

{{< youtube rq57liGu0H4 >}}

**Optimize Amazon EKS Costs with Karpenter and Stormforge**

Sai Vennam and Raj Saha are joined by John Platt from Stormforge to take a look at auto-scaling best practices on Amazon EKS clusters. We'll focus on cluster auto-scaling with open-source Karpenter and pod auto-scaling with Stormforge.

{{< youtube 1pC2oMNOPxY >}}

### Events for your diary

If you are planning any events in 2024, either virtual, in person, or hybrid, get in touch as I would love to share details of your event with readers. 

**Everything Open**
**April 16th-18th, Gladstone Australia**

Everything Open is an open source event where the open source community come together for three days to share updates on their projects and learn about the latest in open technologies from leading community members. The conference will cover a broad range of topics across three days. You can expect to see talks from areas such as the Linux ecosystem, including the Kernel, distros and drivers. There will also be a number of presentations on open source software and open hardware, alongside talks on Galleries, Libraries, Archives and Museums (GLAM), open data, open government, and much more. Another key feature will be talks on building and managing communities around open technologies. I will be attending and doing some open source talks, as well as finding out more about the local open source community.

Check out [the event website](https://aws-oss.beachgeek.co.uk/3nh)for more details, and hope to see some of you there.

**AWS Summit London**
**April 24th, EXCEL London**

If you are heading to the [AWS Summit London](https://aws-oss.beachgeek.co.uk/3t2) then make sure you head over to the open source demo booth over in the AWS for Every App village. We have nine hand selected demos across a broad range of technologies, I whilst I cannot be there myself, I am super excited about this. Find out more about the demos, and the schedule by checking out the post I put together, [Open Source demos at AWS Summit London](https://aws-oss.beachgeek.co.uk/3t1)

**OpenSearchCon Europe**
**May 6th-7th, Berlin Germany**

I am happy to share news of the launch of a European edition of OpenSearchCon, so make sure you mark these dates in your diary. OpenSearchCon Europe has now joined OpenSearchCon North America on our 2024 conference schedule. Read more about the event in the post, [Announcing OpenSearchCon Europe 2024](https://aws-oss.beachgeek.co.uk/3pn)

**Cortex**
**Every other Thursday, next one 16th February**

The Cortex community call happens every two weeks on Thursday, alternating at 1200 UTC and 1700 UTC. You can check out the GitHub project for more details, go to the [Community Meetings](https://aws-oss.beachgeek.co.uk/2h5) section. The community calls keep a rolling doc of previous meetings, so you can catch up on the previous discussions. Check the [Cortex Community Meetings Notes](https://aws-oss.beachgeek.co.uk/2h6) for more info.

**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://aws-oss.beachgeek.co.uk/1az)

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes:  Gabriel Koo, Antoine Descamps, Josh Hart, Amit Upadhyay, Abhishek Pandey, Sankaran Kannappan, Premal Tailor, Kanwaljit Khurmi, Ana Simoes, Hamid Shojanazeri, Less Wright, Alex Iankoulski, Jervin Real, Andries Engelbrecht, Deenbandhu Prasad, Brian Dolan, Nidhi Gupta, Scott Teal, Dipal Mahajan, Akhil B, Ramesh Raghupathy, Sai Vennam, Raj Saha, John Platt, Carlos Santana, Kyle Davis, Srinivas Jasti, Ashok Srirama, Kesha Hietala, Emina Torlak, Ray Krueger, Shrikant Pandhare, Yahav Biran, Vikram Venkataraman, Kulwant Singh, Rich Buggy, Elliott Cordo, Chris Norman, Saifeddine Rajhi, João Galego, and Dakota Lewallen

**Feedback**

Please please please take 1 minute to [complete this short survey](https://www.pulse.aws/promotion/10NT4XZQ). 

### Stay in touch with open source at AWS

Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) for more open source goodness.

One of the pieces of feedback I received in 2023 was to create a repo where all the projects featured in this newsletter are listed. Where I can hear you all ask? Well as you ask so nicely, you can meander over to[ newsletter-oss-projects](https://aws-oss.beachgeek.co.uk/3l8).

Made with ♥ from DevRel
