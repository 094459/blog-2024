---
title: 'AWS open source newsletter #208'
date: '2025-03-30'
tags : [ oss-newsletter, aws open source, Kubernetes, Amazon EKS, Karpenter, Valkey, Amazon Linux, MySQL, Next.js, Swift, PySpark, Apache Iceberg, Amazon Corretto, LangGraph, HBase, Amazon EMR, DuckDB, Starburst, Apache Kafka, PostgreSQL, Wordpress, AWS Lambda Profiler Extension for Java, .NET Aspire ]
canonicalUrl: "https://dev.to/aws/aws-open-source-newsletter-208-43ii"
---

##  Edition #208 - March 2025

Welcome to issue #208 of the AWS open source newsletter, the newsletter where we try and provide you the best open source on AWS content. As always, we have more great new projects to check out, which include an experimental profiler for your serverless Java applications, a bunch of cool projects around Model Context Protocol (MCP), an interesting project around extracting insights from your observation data, projects to help you with your AWS storage services, an interesting project for those of you exploring chaos engineering, some nice generative AI projects that help you explore your code base, and to finish, the usual round up of demo projects which you should go check out. Finally, don't forget to check out the videos as I have a couple of great ones for you in this edition.

The projects will keep you busy until next month for sure, but we also have plenty of reading material in this months newsletter. We feature projects including Kubernetes, Karpenter, Valkey, Amazon Linux, MySQL, Next.js, Swift, PySpark, Apache Iceberg, Amazon Corretto, LangGraph, HBase, Amazon EMR, DuckDB, Starburst, Apache Kafka, PostgreSQL, Wordpress, and .NET Aspire.

As always, get in touch if you want me to feature your projects in this open source newsletter. Until the next time, I will leave you to dive into the good stuff!

**End of life announcements**

On May 30th, 2025, the AWS Cloud Development Kit (CDK) will no longer support Node.js 14.x and 16.x, which reached end of life on 4/30/2023 (14.x) and 9/11/2023 (16.x). This change applies to all AWS CDK components that depend on Node.js, including the AWS CDK CLI, the Construct Library, and broader CDK ecosystem projects such as JSII, Projen, and CDK8s. Check out the blog post from Adam Keller for more details, [Announcing the end of support for Node.js 14.x and 16.x in AWS CDK](https://aws-oss.beachgeek.co.uk/49r).

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution. The projects mentioned here do not represent any formal recommendation or endorsement, I am just sharing for greater awareness as I think they look useful and interesting!*

### Tools

**aws-lambda-java-profiler**

[aws-lambda-java-profiler](https://aws-oss.beachgeek.co.uk/4a1) is an experimental (currently) release that provides a new capability that helps builders gain deep performance insights into their Lambda functions. The Lambda Profiler enables you to analyse your serverless applications with precision and ease. What can it do I can hear you all saying. It's current capabilities include:

* Generate detailed flame graphs for every function invocation
* Leverage low overhead sampling async-profiler technology with no safepoint bias
* Automatically store profiling data in your designated Amazon S3 bucket

Getting started is simple - just attach the Lambda layer to your function. No code changes required. This new capability helps you optimise cost and performance, identify bottlenecks, and deliver better experiences to your customers. It's another example of how we're listening to our builders and delivering the tools they need to innovate faster.

Check out the Community Blogs section below for some early content on this project.

**observation-extractor**

[observation-extractor](https://aws-oss.beachgeek.co.uk/4at) is a tool for collecting observations from data. Observations are useful bits of data related to questions that you define that is extracted from the data you pass in. Use Observation Extractor to process pdf (and maybe someday other files) into formats like csv (and later parquet) to turn unstructured documents into structured observations that you can query and use directly or through your application. When you output to a format like csv or parquet, observations are the row level records.

Observation Extractor takes an unstructured data file as input (like a pdf) and outputs a list of Observation objects. Each observation includes standard fields that are extracted from the document together with metadata like the document name and page number.

You can populate observations into a datastore and make them available to your human and AI users. They can be queried based on metadata like date and the specific questions they relate too. You can define question sets that represent thought process of a subject-matter-expert coming up to speed on this case to start mapping a document into useful observations.

![overview of architecture](https://github.com/awslabs/observation-extractor/blob/main/assets/Observer.png?raw=true)

**fsx-to-s3-int**

[fsx-to-s3-int](https://aws-oss.beachgeek.co.uk/4a9) is a new tool from Steve Jones that helps AWS users analyse their FSx for NetApp ONTAP (FSxN) volume usage patterns to estimate potential cost savings when migrating to Amazon S3 Intelligent-Tiering. It collects and analyses metrics such as storage usage, access patterns, and operations to provide insights for data migration planning. Steve has put together a blog post that helps you get started, so go check out [Unlocking Cloud Savings: Your Guide to FSx and S3 Intelligent-Tiering with Python Magic!](https://aws-oss.beachgeek.co.uk/4aa)

**s3-delta-download**
 
[ s3-delta-download](https://aws-oss.beachgeek.co.uk/4af) is a new tool for interacting with your Amazon S3 buckets, that will help anyone who is encountering current limitations of the 's3 sync', specifically that it does not yet support using a non-directory key prefix. This means that it will only download those files it does not already have, skipping files that are not already in your local directory.

The README provide a nice example of how this works, and also covers installation dependencies you need (it requires .NET SDK or later).

**aws-cost-explorer-mcp-server**

[aws-cost-explorer-mcp-server](https://aws-oss.beachgeek.co.uk/4ac) builds on the current wave of excitement around Model Context Protocol (MCP) that provides a powerful open-source tool that brings natural language querying to your AWS spending data. Ask questions like "What was my EC2 spend yesterday?" or "Break down my Bedrock usage by model" and get detailed answers through Claude. It helps track cloud costs across services, identifies expensive resources, and provides deep insights into your Amazon Bedrock model usage.

Nice detailed README will get you going, but you can also check out the demo video before hand to see if this is something you want to try out yourself

{{< youtube WuVOmYLRFmI >}}

**aws-mcp**

[aws-mcp](https://aws-oss.beachgeek.co.uk/4ag) is a project from Rafal Wilinski that enables AI assistants like Claude to interact with your AWS environment through MCP. This allows for natural language querying and management of your AWS resources during conversations. 

![example prompt using aws-mcp to find out about costs](https://github.com/RafalWilinski/aws-mcp/blob/main/images/aws-mcp-demo.png?raw=true)

**mcp-lambda-layer**

[mcp-lambda-layer](https://aws-oss.beachgeek.co.uk/4ab) is project that uses a Node.js package that provides MCP (Model Context Protocol) server infrastructure for AWS Lambda functions with SSE support. The repo provides example code for tools and prompts which should get you started and simplify how you might provide these to your MCP clients. Check out the README for other important notes.

**awsesh**

[awsesh](https://aws-oss.beachgeek.co.uk/4ad) is a command line tool for managing your AWS SSO sessions for those of you who are using AWS IAM Identity Centre (IdC). Whilst the repo provides pre built binaries for Mac, Linux, and Windows, you can also build from source too. There is a brief README with videos showing how this works - it is pretty simple to get up and running. If you are not using a vanity name for your IdC, then just use the prefix you see on the IdC dashboard when configuring this tool.

**node-red-contrib-aws-bedrock**

[node-red-contrib-aws-bedrock](https://aws-oss.beachgeek.co.uk/4ae) is a project from my colleague Kelsea Blackweel that create a new node type within node-red (my favourite open source project ever!) that allows you to integrate Amazon Bedrock into your flows. So cool!
 
**sample-convert-codebase-to-graphrag**

[sample-convert-codebase-to-graphrag](https://aws-oss.beachgeek.co.uk/4ak) is a demo to show how to leverages AI to analyze, index, and query code repositories. It creates a searchable graph representation of code structures, enabling developers to explore and understand complex codebases efficiently. This project combines several AWS services, including Lambda, Neptune, OpenSearch, and Bedrock, to process code repositories, generate metadata, and provide powerful search capabilities. The system is designed to handle large-scale code analysis tasks and offer semantic code search functionality. It uses CDK to simplify how to deploy this in your own AWS environments.

**chorus**

[chorus](https://aws-oss.beachgeek.co.uk/4aq) is a new easy-to-use framework for building scalable solutions with LLM-driven multi-agent collaboration. Chorus allows you to develop and test solutions using multi-agent collaboration with zero or minimal coding. Chorus provides a multi-agent playground for easy visualisation and testing. Finally, Chorus helps you deploy your solution to Amazon Bedrock Agents with a single command (coming soon).

**amazon-kinesis-video-streams-dcep**

[amazon-kinesis-video-streams-dcep](https://aws-oss.beachgeek.co.uk/4am) is the repo for the Data Channel Establishment Protocol (DCEP) library.  DCEP is a simple protocol for establishing symmetric data channels between WebRTC peers. It uses a two-way handshake and allows sending of user data without waiting for the handshake to complete. The peer that initiates opening a data channel selects a stream identifier for which the corresponding incoming and outgoing streams are unused and sends a DATA_CHANNEL_OPEN message on the outgoing stream. The peer responds with a DATA_CHANNEL_ACK message on its corresponding outgoing stream. Then the data channel is open. DCEP messages are sent on the same stream as the user messages belonging to the data channel. The demultiplexing is based on the SCTP Payload Protocol Identifier (PPID), since DCEP uses a specific PPID.

**chaos-machine**

[chaos-machine](https://aws-oss.beachgeek.co.uk/4ao) is a complete chaos engineering workflow that enables customers to run controlled chaos experiments and test hypotheses related to system behaviour. Chaos Machine uses metric and alarm data from both Amazon CloudWatch and Prometheus as inputs to evaluate system behaviour before, during, and after the experiment. The Chaos Machine provides a simple, consistent way to organise and execute chaos experiments, and is appropriate to use for both building and conducting ad-hoc experiments or integrating into more sophisticated automation pipelines. Chaos Machine uses the AWS Fault Injection Service (FIS) to run controlled experiments, and AWS Step Functions and AWS Lambda for orchestration and execution.

![chaos machine architecture](https://github.com/awslabs/chaos-machine/blob/main/_docs/chaos-machine.png?raw=true)

### Demos, Samples, Solutions and Workshops

**wio-from-diagram-to-code-with-amazon-q-developer**

[wio-from-diagram-to-code-with-amazon-q-developer](https://aws-oss.beachgeek.co.uk/4a8) this project from AWS Community Builder Olivier Lemaitre that demonstrates how you can generate diagrams from an application code, but also how to generate code from diagrams using Amazon Q Developer in the Visual Studio Code IDE.

![example diagram from repo](https://github.com/welcloud-io/wio-from-diagram-to-code-with-amazon-q-developer/blob/main/screenshots/vscode-bigpicture.png?raw=true)

**eks_demo**

[eks_demo](https://aws-oss.beachgeek.co.uk/4ah) is a nice demo repo from former colleague Seth Elliot that provides a ready to go set of AWS resources via Terraform, that deploys an Amazon EKS cluster with a sample guestbook application using a number of supporting AWS services (check out the repo for more info). It is intended as an easy to understand environment for you to study and learn.

**Bedrock-MEAI-Sample**

[Bedrock-MEAI-Sample](https://aws-oss.beachgeek.co.uk/4ai) is just what you need if you are looking to integrate Amazon Bedrock with .NET MAUI, providing sample code that demonstrates how to create a chat client in a .NET MAUI mobile app.

**sample-aws-dax-go-v2**

[sample-aws-dax-go-v2](https://aws-oss.beachgeek.co.uk/4an)  is the official AWS DAX SDK for the Go programming language. In addition to this, [sample-aws-dax-go-v2-sample](https://aws-oss.beachgeek.co.uk/4al)is some sample code / application showing how to use DynamoDB Accelerator (DAX) Go Language SDK Client.


**2025-bootiful-aws-ai**

[2025-bootiful-aws-ai](https://aws-oss.beachgeek.co.uk/4aj) is just what you need if you are looking to explore the wonderful world of MCP in Java. James and Josh have put together this simple demo that uses the recently GAd Spring Boot AI libraries to make creating MCP clients and servers a breeze.

**amazon-eks-chaos**

[amazon-eks-chaos](https://aws-oss.beachgeek.co.uk/4ar) this repo shows the steps involved to implement running chaos experiments on micro services in Amazon EKS using AWS Fault Injection Simulator with ChaosMesh and LitmusChaos. You can read about this in the supporting blog post,[ Chaos engineering on Amazon EKS using AWS Fault Injection Simulator](https://aws-oss.beachgeek.co.uk/4as).

### AWS and Community blog posts

**This weeks essential reading**

Here are the posts that I think are essential reads, so start here.

* [Develop and test AWS Glue 5.0 jobs locally using a Docker container](https://aws-oss.beachgeek.co.uk/49o) - definitely check this out if you are doing any work with AWS Glue, as it provides details of how you can develop and test locally using some curated container images we have put together [hands on]
* [End of support notifications and enhanced discoverability for Amazon EKS](https://aws-oss.beachgeek.co.uk/49t) - provides a hands on guide can help you set up a robust system using AWS services to provide proactive end of standard support notifications [hands on]
* [Building and Debugging .NET Lambda applications with .NET Aspire (Part 1)](https://aws-oss.beachgeek.co.uk/49x) and [Building and Debugging .NET Lambda applications with .NET Aspire (Part 2)](https://aws-oss.beachgeek.co.uk/49w) - dives deep into how to use .NET Aspire to run and debug .NET Lambda functions locally, and then how to incorporate .NET Aspire’s programming model for connecting additional components and sharing best practices across Lambda functions [hands on]

**Community round up**

Each week I spent a lot of time reading posts from across the AWS community on open source topics. In this section I share what personally caught my eye and interest, and I hope that many of you will also find them interesting.

If you checked the projects above you will have noticed that we open sourced  the [AWS Lambda Profiler Extension for Java](https://aws-oss.beachgeek.co.uk/4a1) (thanks Mark Sailes for giving me the heads up). AWS Hero Vadym Kazulkin was quick to take the opportunity to extend his awesome series of posts on running Java on AWS with his latest, [AWS Lambda Profiler Extension for Java- Part 1 Introduction](https://aws-oss.beachgeek.co.uk/4a2), showing you how to build this and then providing an example application so you can see it in action. Very nice post as always.

If you are a Linux user (hands up!) then there were a few posts of interest, including some of mine. First up is Curtis Evans post on how you can use AI Coding Assistants like Amazon Q Developer on the CLI, to rediscover the power and productivity that working with Linux gives you in his post, [Supercharge your Linux environment with Amazon Q Developer CLI ](https://aws-oss.beachgeek.co.uk/4a3). On a different note, I put together [Essential guide to installing Amazon Q Developer CLI on Linux](https://aws-oss.beachgeek.co.uk/4a4) that walks you through how you can install the Amazon Q Developer CLI in different Linux systems (both GUI and headless) but also how you can compile it from source (did you know it was an open source project?).

From Linux we go to Cloud native land, with AWS Community Builder Sunny Bhambhani sharing his experience in securing your Kubernetes environments using CIS Benchmarks, in his post [Kubernetes hardening made easy: Running CIS Benchmarks with kube-bench ](https://aws-oss.beachgeek.co.uk/4a5).

As some readers might have noticed, I am spending more time with AI Coding Assistants like Amazon Q Developer, and am finding they are excellent tools to help open source developers. Shashank C shared how he used it to help him deploy WordPress on AWS with Terraform in his post, [Zero to Hero: Automate installation of WordPress CMS with Terraform and Amazon Q](https://aws-oss.beachgeek.co.uk/4a6). I actually had a different use case in mind, taking an old PHP project and using Amazon Q Developer to refactor the code to Python. It not only worked, but the whole process was done in under an hour. Check out my post on this, [From PHP to Python - porting a Reddit clone with the help of Amazon Q Developer](https://dev.to/aws/from-php-to-python-porting-a-reddit-clone-with-the-help-of-amazon-q-developer-23g).

To finish this round up I want to share a post on something I am spending a lot of time exploring these days, Model Context Protocol, or MCP as it is more commonly referred to. These provide large language models (LLMs) with super powers. AWS Community Builder Paul Santus put together [Introducing AWS Service Reference Information MCP Server ](https://aws-oss.beachgeek.co.uk/4a7) which implements a tool that provides querying of Service Reference Information, covering IAM Actions, Resources and Condition Keys, that should help reduce the hallucinations when prompting on these topics. Very cool idea.

**Cloud Native**

* [Effortless application modernization: migrate to Amazon EKS with existing NLB setup](https://aws-oss.beachgeek.co.uk/49h) - explores hybrid deployment pattern that provides a smooth, low-risk migration path from Amazon EC2 to Amazon EKS [hands on]
* [Run GenAI inference across environments with Amazon EKS Hybrid Nodes](https://aws-oss.beachgeek.co.uk/49k) - describes a proof of concept for using a single EKS cluster to run AI inference on-premises with EKS Hybrid Nodes and in the AWS Cloud with Amazon EKS Auto Mode [hands on]

![ A diagram providing a high-level overview of an EKS cluster with both EKS Hybrid Nodes and EKS nodes in-Region.](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2025/03/18/Picture2-4.png)

* [Modify Amazon EBS volumes on Kubernetes with Volume Attributes Classes](https://aws-oss.beachgeek.co.uk/49z) - looks at how to modify Amazon Elastic Block Store (Amazon EBS) volumes on Kubernetes without application downtime [hands on] 

**Data and Analytics**

* [Build multi-Region resilient Apache Kafka applications with identical topic names using Amazon MSK and Amazon MSK Replicator](https://aws-oss.beachgeek.co.uk/49i) - demonstrates how to enhance Kafka resilience by setting up a secondary MSK cluster in another Region and synchronizing it with the primary cluster using MSK Replicator [hands on]
* [Express brokers for Amazon MSK: Turbo-charged Kafka scaling with up to 20 times faster performance](https://aws-oss.beachgeek.co.uk/49s) - walk syou through the implementation of MSK Express brokers, highlighting their core features, benefits, and best practices for rapid Kafka scaling 

* [Build a managed Apache Iceberg data lake using Starburst and Amazon S3 Tables](https://aws-oss.beachgeek.co.uk/49p) - showcases building a data lake on Starburst and Amazon S3, and how the integration builds on Starburst’s long-standing focus on Apache Iceberg and the benefits of automated table maintenance tasks by Amazon S3 Tables [hands on]
* [Using Amazon S3 Tables with Amazon Redshift to query Apache Iceberg tables](https://aws-oss.beachgeek.co.uk/49j) - show how to get started with S3 Tables and Amazon Redshift Serverless for querying data in Iceberg tables, that covers how to set up S3 Tables, load data, register them in the unified data lake catalog, set up basic access controls, and query the data using Amazon Redshift [hands on]
* [Streamlining access to tabular datasets stored in Amazon S3 Tables with DuckDB](https://aws-oss.beachgeek.co.uk/49m) - looks at how to use DuckDB to read Iceberg tables stored in S3 table buckets using Amazon SageMaker Lakehouse Iceberg REST endpoint and AWS Lake Formation permissions on your local machine [hands on]
* [Implement Amazon EMR HBase Graceful Scaling](https://aws-oss.beachgeek.co.uk/49l) - provides example and code that demonstrate how to handle Amazon EMR HBase scaling gracefully, especially in use cases where you might be using HBase on EMR with Spot Instances [hands on]
* [Design patterns for implementing Hive Metastore for Amazon EMR on EKS](https://aws-oss.beachgeek.co.uk/49u) - goes through the architecture patterns and demonstrate their implementation using Amazon EMR on EKS with Spark Operator job submission type, guiding you through the complexities to help you choose the best approach for your use case [hands on]

* [Use pgactive for rolling major version upgrades in Amazon RDS for PostgreSQL](https://aws-oss.beachgeek.co.uk/49n) - explores how pgactive can perform rolling major version upgrades for Amazon Relational Database Service (Amazon RDS) for PostgreSQL, allowing for a smoother transition with reduced impact on your applications [hands on]

**Other posts to check out**

* [Build a Multi-Agent System with LangGraph and Mistral on AWS](https://aws-oss.beachgeek.co.uk/49v) - looks at how to use LangGraph and Mistral models on Amazon Bedrock to create a powerful multi-agent system that can handle sophisticated workflows through collaborative problem-solving [hands on]
* [53 new or updated datasets available on the Registry of Open Data on AWS](https://aws-oss.beachgeek.co.uk/49y) - shares the latest data sets that available for developers to explore and use, that cover a wide range of use cases: climate and weather, geospatial, life sciences, and machine learning
* [Port .NET Framework workloads to Linux with Amazon Q Developer, Part 2: Test Projects](https://aws-oss.beachgeek.co.uk/4a0) - is the first in a series of posts that explores how to port different kinds of .NET Framework projects to cross-platform .NET with Amazon Q Developer .NET transformation (currently in public preview), enabling you to modernize your Windows-based .NET Framework solutions to run on Linux can reduce operational costs by up to 40%. [hands on]


### Quick updates

**Amazon Corretto**

Corretto 24 is now available for download. Amazon Corretto is a no-cost, multi-platform, production-ready distribution of OpenJDK. Corretto 24 is an OpenJDK 24 Feature Release, which will be supported through October, 2025.

OpenJDK 24 introduces enhanced performance with two new experimental features: the Generational Shenandoah garbage collector, designed to improve sustainable throughput, load-spike resilience, and memory utilization, and Compact Object Headers, designed to improve heap usage by shrinking object headers from between 96 and 128 bits down to 64 bits on 64-bit architectures. Additionally, this release includes Ahead-of-Time Class Loading & Linking, designed to improve startup time by making the classes of an application instantly available, Synchronize Virtual Threads without Pinning, designed to eliminate nearly all cases of virtual threads being pinned to platform threads, Quantum-Resistant Module-Lattice-Based Key Encapsulation Mechanism, designed to be secure against future quantum computing attacks.

Click on the [Corretto home page to download Corretto 24](https://aws-oss.beachgeek.co.uk/49f).

> As a bonus, if you are looking to get help in migrating to newer versions of Java, check out how you can use Amazon Q Developer to help you. My colleague Brian Beach has put together a blog post sharing how you can use this to upgrade applications to Java 21, in his post, [Announcing support for upgrades to Java 21 in Amazon Q Developer](https://aws-oss.beachgeek.co.uk/49q).

**Apache Iceberg**

Amazon S3 Tables now offer table management APIs that are compatible with the Apache Iceberg REST Catalog standard, enabling any Iceberg-compatible application to easily create, update, list, and delete tables in an S3 table bucket. These new table management APIs, that map directly to S3 Tables operations, make it easier for you to get started with S3 Tables if you have a custom catalog implementation, need only basic read and write access to tabular data in a single S3 table bucket, or use an APN partner-provided catalog. For unified data management across all of your tabular data, data governance, and fine-grained access controls, you can use S3 Tables with SageMaker Lakehouse. The new table management APIs are available in all AWS Regions where S3 Tables are available, at no additional cost.

**PySpark**

AWS announced the general availability of PySpark in AWS Clean Rooms, enabling companies and their partners to run sophisticated analytics across large datasets using PySpark, the Python API for Apache Spark. With this launch, you and your partners can bring PySpark code and libraries to an AWS Clean Rooms collaboration and run advanced analyses without having to share underlying data or proprietary analysis methods. For example, an advertising measurement provider can use PySpark in AWS Clean Rooms to run their custom algorithms across multiple publisher datasets simultaneously to measure ad effectiveness. Similarly, a pharmaceutical company can run their proprietary algorithms and libraries across multiple healthcare provider datasets with appropriate patient consent to evaluate drug adherence across clinical trials, without sharing their proprietary data.

**Swift**

Amplify Swift now supports sharing authentication state across multiple apps by leveraging keychain access groups. This new feature allows developers to manage a single authentication session across all Swift-based applications and extensions within the same access group. Developers can now configure Amplify to store authentication information in a shared keychain, with built-in support for migrating existing sessions.

Regardless of platform, users only need to sign in once to access any application or extension within the same access group. This feature is particularly valuable for developers creating families of Swift applications that require consistent authentication states across their ecosystem, including iOS, macOS, watchOS, and tvOS apps. This capability is now available for all Swift applications using Amplify Swift.

**Next.js**

AWS Amplify now supports HttpOnly cookies for server-rendered Next.js applications when using Amazon Cognito's Managed Login. This enhancement builds upon existing cookie functionality in server-rendered sites, opting in to the HttpOnly attribute strengthens your application's security posture by blocking client-side JavaScript from accessing cookie contents.

With HttpOnly cookies, your applications gain an additional layer of protection against cross-site scripting (XSS) attacks. This ensures that sensitive information remains secure and will only be transmitted between the browser and the server, and is particularly valuable when handling authentication tokens in your web applications. The contents of cookies with HttpOnly attributes can only be read by the server, requiring your requests to flow through the server before reaching other services. This feature is now available in all AWS regions where AWS Amplify and Amazon Cognito are supported.

**MySQL**

Amazon RDS for MySQL now supports MySQL Innovation Release 9.2 in the Amazon RDS Database Preview Environment, allowing you to evaluate the latest Innovation Release on Amazon RDS for MySQL. You can deploy MySQL 9.2 in the Amazon RDS Database Preview Environment that has the benefits of a fully managed database, making it simpler to set up, operate, and monitor databases. MySQL 9.2 is the latest Innovation Release from the MySQL community. MySQL Innovation releases include bug fixes, security patches, as well as new features. MySQL Innovation releases are supported by the community until the next major & minor release, whereas MySQL Long Term Support (LTS) Releases, such as MySQL 8.0 and MySQL 8.4, are supported by the community for up to eight years. Please refer to the MySQL 9.2 [release notes](https://aws-oss.beachgeek.co.uk/49e) for more details about this release. The Amazon RDS Database Preview Environment supports both Single-AZ and Multi-AZ deployments on the latest generation of instance classes. Amazon RDS Database Preview Environment database instances are retained for a maximum period of 60 days and are automatically deleted after the retention period. Amazon RDS database snapshots that are created in the preview environment can only be used to create or restore database instances within the preview environment.

In more MySQL news, Amazon RDS for MySQL announced Amazon RDS Extended Support minor version 5.7.44-RDS.20250213. We recommend that you upgrade to this version to fix known security vulnerabilities and bugs in prior versions of MySQL.  Amazon RDS Extended Support provides you more time, up to three years, to upgrade to a new major version to help you meet your business requirements. During Extended Support, Amazon RDS will provide critical security and bug fixes for your MySQL databases on Aurora and RDS after the community ends support for a major version. You can run your MySQL databases on Amazon RDS with Extended Support for up to three years beyond a major version’s end of standard support date.  Learn more about Extended Support [in the Amazon RDS User Guide](https://aws-oss.beachgeek.co.uk/49g).

**Amazon Linux 2023**

Amazon Elastic Container Service (Amazon ECS) today introduced GPU-optimised Amazon Machine Image (AMI) for Amazon Linux 2023 (AL2023). This new offering enables customers to run GPU-accelerated containerised workloads on Amazon ECS while leveraging improved security features and newer kernel version available on AL2023.

The new ECS GPU-optimised AMI is built on the minimal AL2023 base AMI and includes NVIDIA drivers, NVIDIA Fabric Manager, NVIDIA Container Toolkit, and other essential packages needed to run GPU-accelerated container workloads. The new AMI supports a wide range of NVIDIA GPU architectures including Ampere, Turing, Volta, Maxwell, Hopper, and Ada Lovelace, and works out-of-the-box with no additional configuration required. The new AMI is designed for GPU-accelerated applications such as machine learning (ML) and artificial intelligence (AI) workloads running on Amazon ECS. The ECS GPU-optimised AL2023 AMI is now available in all AWS regions.

**Kubernetes**

A couple of updates this month for those who want to keep up with Kubernetes news.

First is news that Amazon EMR on EKS now has support for Amazon EKS Pod Identity, simplifying the setup of IAM permissions required by EMR on EKS jobs to access other AWS resources. With this launch, you can configure IAM permissions through a single API call, significantly reducing complexity and potential for errors. The new feature also allows you to leverage IAM roles across multiple clusters without the need to update IAM trust policies for use in new clusters, improving reusability and operational efficiency. To run workloads on Amazon EMR on EKS, customers need to create a job execution IAM role that pods in EKS cluster will use to interact with other AWS resources such as Amazon S3 buckets. Previously, customers had to perform multiple configuration steps such as creating an OIDC identity provider and updating IAM’s role trust policy. Role trust policy size also limited the number of EKS clusters that customers could reuse a job execution role across. Now, customers can configure IAM permissions through a single API call and reuse an IAM role across multiple clusters without additional configuration updates.

AWS also announced extended support for Kubernetes versions for Amazon Elastic Kubernetes Service Anywhere (Amazon EKS Anywhere). With extended support for Kubernetes versions for Amazon EKS Anywhere, you continue to receive security patches for clusters on any Kubernetes version for up to 26 months after the version is released in Amazon EKS Anywhere. Extended support for Kubernetes versions for Amazon EKS Anywhere is available for Kubernetes versions 1.28 and above. Standard support begins when a Kubernetes version becomes available in Amazon EKS Anywhere, and continues for 14 months - the same as the upstream Kubernetes project support window. After this time period, Amazon EKS Anywhere continues to include patches for Kubernetes versions for an additional 12 months. Cluster administrators and security teams using Amazon EKS Anywhere now get more time to plan Kubernetes upgrades, without compromising on the security posture of their clusters.

### Videos of the week

**Hands on with Amazon EKS Auto Mode**

Carlos Santana, Alex Kestner, and Todd Neal show you how Amazon EKS Auto Mode fully automates Kubernetes cluster management for compute, storage, and networking on AWS with a single click

{{< youtube rMOtrTyJdFo >}}

**Kubernetes Karpenter Vs AWS EKS Auto**

In this video, Cloud With Raj covers the differences and similarities between EKS Auto and Karpenter, and provides his views on when to use what.

{{< youtube WtL6WHQldYc >}}

**AWS in-memory solutions and Valkey open-source innovation**

Prasad Matkar, Maria Gutovsky, and Paul Ross show you how to implement Valkey on AWS through demonstrations covering cluster creation, data migration and application integration using the optimised Valkey client library.

{{< youtube ipu5gEiA4aw >}}

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes: Prasad Matkar, Maria Gutovsky, Paul Ross , Carlos Santana, Alex Kestner, Todd Neal, Henrique Santana,  Luis Felipe,  Subham Rakshit, Jonathan Katz, Satesh Sonti, Robert Northard, Eric Chapman, Elamaran Shanmugam, Yu-Ting Su, Chris Li, Hsing-Han Wang, Cheng Wang, Anupriti Warade, Yuri Zarubin, Santosh Bhupathi, Chirag Dave, Yuya Ebihara, Aritra Gupta, Antony Prasad Thevaraj, Adam Keller, Brian Beach, Masudur Rahaman Sayem, Praseeda Sathaye, AJ Davis, Arvind Viswanathan, Avinash Desireddy, Suvojit Dasgupta, Norm Johanson,  Kevin Liu, Jens-Uwe Walther, Drew Sirenko, David Pallmann, Paul Santus, Curtis Evans, Shashank C, Sunny Bhambhani, Vadym Kazulkin, Mark Sailes, Steve Jones, Rafal Wilinski, Kelsea Blackweel, and Olivier Lemaitre.

**Feedback**

Please please please take 1 minute to [complete this short survey](https://www.pulse.aws/promotion/10NT4XZQ). 

### Stay in touch with open source at AWS

Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) for more open source goodness.

One of the pieces of feedback I received in 2023 was to create a repo where all the projects featured in this newsletter are listed. Where I can hear you all ask? Well as you ask so nicely, you can meander over to[ newsletter-oss-projects](https://aws-oss.beachgeek.co.uk/3l8).

Made with ♥ from DevRel