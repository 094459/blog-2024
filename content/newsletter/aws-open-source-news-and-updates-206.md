---
title: 'AWS open source newsletter #206'
date: '2025-01-27'
tags : [ oss-newsletter, aws open source,  AWS CDK, Cedar, Swift, Apache Iceberg, Valkey, Kubernetes, Amazon EKS, Karpenter, OpenShift, ROSA, Bottlerocket, TensorFlow, Triton, MySQL, PostgreSQL, MariaDB, InfluxDB, Apache Kafka, Amazon EMR, Apache Spark, dbt, OpenZFS, AWS Amplify, Grafana, OpenSearch, Apache ActiveMQ, Powertools for AWS Lambda, Backstage, Apache Flink, Prometheus]
canonicalUrl: "https://dev.to/aws/aws-open-source-newsletter-206-3l9f"
---

##  Edition #206

Happy New Year and welcome to issue #206 of the AWS open source newsletter, the newsletter where we try and provide you the best open source on AWS content.  As this is the first edition post re:Invent, you will find a lot of content showcasing all the new open source stuff that AWS has released, so there is plenty of really cool stuff to get stuck into - whether you are cloud native and want to know more about Amazon EKS Auto Mode, or more a data guru that is super excited about Apache Iceberg support in Amazon S3 Tables.

As always, we start with a selection of new open source projects from around AWS and the Community. It is safe to say that you have all been very busy over the last few weeks. This editions projects have something for everyone, including CDK constructs to help you simplify building your own BlueSky Personal Data Server and VSCode servers, Cedar on Kubernetes, planning tools for your ECS workloads, and a bunch of generative AI tools of course.

You can also catch up on the latest open source content as we feature projects including AWS CDK, Cedar, Swift, Apache Iceberg, Valkey, Kubernetes, Karpenter, OpenShift, Bottlerocket, TensorFlow, Triton, MySQL, PostgreSQL, MariaDB, InfluxDB, Apache Kafka, Amazon EMR, Apache Spark, dbt, OpenZFS, AWS Amplify, Grafana, OpenSearch, Apache ActiveMQ, Powertools for AWS Lambda, Backstage, Apache Flink, and Prometheus. That lot should keep you very busy.

If you are coming to FOSDEM this weekend then get in touch. I will be manning the open source data analytics devroom with my fellow open source nerds Javier and Jaromir. Look forward to seeing some of you I hope!

As always, get in touch if you want me to feature your projects in this open source newsletter. Until the next time, I will leave you to dive into the good stuff!

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution. The projects mentioned here do not represent any formal recommendation or endorsement, I am just sharing for greater awareness as I think they look useful and interesting!*

### Tools

**cedar-access-control-for-k8s**

[cedar-access-control-for-k8s](https://aws-oss.beachgeek.co.uk/47k) is a very very cool project from Micah Hausler, that extends Cedar to the Kubernetes control plane and allows you to implement fine grain policies in Cedar that allow you to have much greater control and flexibility of authorisation within your Kubernetes environments. If you are using Kubernetes, then reviewing this project is a must. Check out the video in the Videos section at the end for more info, where Micah walks you through how this works in more detail.

**dynamodb-parallel-scan**

[dynamodb-parallel-scan](https://aws-oss.beachgeek.co.uk/47l) is a new node library from shelfio that looks to speed up scanning your DynamoDB tables, through parallelism. Vlad Holubiev has put together a blog post, [How to Scan a 23 GB DynamoDB Table in One Minute](https://aws-oss.beachgeek.co.uk/47m) where he shares more details on how this library works, how to get started, as well as some benchmarks he has done.

**local-k8s**

[local-k8s](https://aws-oss.beachgeek.co.uk/47p) is the latest open source project from long time open source developer [Damon Cortesi](https://bsky.app/profile/dacort.velocipig.com/post/3ldmltlkncs2m), who "Poked around with a local environment for Spark on K8s (using KIND)" and shows you how to get Amazon S3 Tables working on OSS Spark. A great place to start if you want to quickly see how this works for your existing open source analytics tools.

**ecs-will-it-fit**

[ecs-will-it-fit](https://aws-oss.beachgeek.co.uk/47h) (or wily for short) is a new project from my good friend Ivica Kolenkaš, that provides a very useful tool for those of you using Amazon ECS. It is a CLI tool that helps you answer the question: "Will this ECS service fit on my ECS cluster backed by EC2 instances?". It does so by mimicking1 the selection process that the ECS scheduler performs while selecting suitable container instances for your service. Nice detailed README provides everything you need to know about how to use this cli. This is in alpha stage, so if you give it a go, make sure to pass on your feedback to Ivica.

**cdk-vscode-server**

[cdk-vscode-server](https://aws-oss.beachgeek.co.uk/47j) is a new CDK construct from Manuel Vogel that provides a speed way to provision VSCode servers on AWS. Check out [his LinedIn post here](https://www.linkedin.com/posts/manuel-vogel_aws-cdk-cdkconstruct-ugcPost-7285010738505523201-YbLw/?utm_source=share&utm_medium=member_ios) for more details, as well as the detailed README. I have done this in the past with CloudFormation (check out my [gist here](https://gist.github.com/094459/0dc0eefcffbbc2c843e11e96940c2011)) but will be switching over to this construct from now on.

**bluesky-pds-cdk**

[bluesky-pds-cdk](https://aws-oss.beachgeek.co.uk/47x) if you are looking to deploy a self-hosted a fully containerized, serverless Bluesky Personal Data Server (PDS) on AWS, then this is the repo for you. It provides an opinionated AWS CDK construct that makes deploying this on AWS a breeze.

**gh-folder-dl**

[gh-folder-dl](https://aws-oss.beachgeek.co.uk/47i) is a handy tool from my colleague Denis Traub, a Python library and CLI tool for downloading files from GitHub repository folders, with recursive support and smart caching. It tracks downloaded files in a SQLite database to avoid re-downloading unchanged files and maintains the original directory structure. Denis has provided helpful examples of how to use this in the README, so go check it out.

**terraform-aws-vulne-soldier**

[terraform-aws-vulne-soldier](https://aws-oss.beachgeek.co.uk/47f) is a new project from Victor Omolayo that provides an AWS EC2 vulnerability remediation tool designed to automate the process of patching nodes managed by AWS Systems Manager. He has put together a blog post, [vulne-soldier: AWS EC2 Vulnerability Remediation Tool](https://aws-oss.beachgeek.co.uk/47g) that provides more detail on the project and background as to why he created it as well as how to get started.

**vpcshark**

[vpcshark](https://aws-oss.beachgeek.co.uk/47q) is a recent project from AWS Hero Aidan Steele, that provides a Wireshark extcap to make ad hoc mirroring of AWS EC2 traffic easier. Check out the README to find out some more details as to why he open sourced this project.

**mcp-server-aws**

[mcp-server-aws](https://aws-oss.beachgeek.co.uk/47r) is a project from Rishi Kavikondala that provides a  [Model Context Protocol](https://aws-oss.beachgeek.co.uk/47s) server implementation for AWS operations that currently supports S3 and DynamoDB services. All operations are automatically logged and can be accessed through the audit://aws-operations resource endpoint.

**chat-cli**

[chat-cli](https://aws-oss.beachgeek.co.uk/47o) is a terminal based program that lets you interact with LLMs available on Amazon Bedrock. You can install and run via source or for ease, Homebrew. The README provides you with more details including how to configure the application. If you want an easy, text base way to interact with the foundational models you run via Amazon Bedrock, check this out.

**abc**

[abc](https://aws-oss.beachgeek.co.uk/47t) is an AI bash tool that integrates with Amazon Bedrock as a foundation model provider. This tool will generate shell command(s) from natural language description using which ever LLM (generative AI) you configure, and place on the next shell prompt for editing and execution. Plenty of details in the README on how to configure and run this, so give it a go if you are looking for something that integrates with Amazon Bedrock.

**llm-test-mate**

[llm-test-mate](https://aws-oss.beachgeek.co.uk/47v) is a project from my colleague Danilo Poccia that is a simple testing framework to evaluate and validate LLM-generated content using string similarity, semantic. Check out the README for a list of features currently supported, as well as examples of how to use it. The README really is a thing of beauty, and I wish more projects provided as clear and detailed info as this project.
 
**projen-vitest**

[projen-vitest](https://aws-oss.beachgeek.co.uk/47n) is a new component for Projen from Niko Virtala that helps you switch from Jest to Vitest in your Projen managed projects. Depending on your configuration, it should be more or less a drop-in replacement. Check out and follow [Niko here](https://bsky.app/profile/nikovirtala.io/post/3lejn3leh4k2b)

**activerecord-dsql-adapter**

[activerecord-dsql-adapter](https://aws-oss.beachgeek.co.uk/47u) is a new project from Samuel Cochran
 that provides the beginnings of an Active Record connection adapter for Amazon's AWS Aurora DSQL database.

### Demos, Samples, Solutions and Workshops

**swift-chat**

[swift-chat](https://aws-oss.beachgeek.co.uk/47y)  is a fast and responsive AI chat application developed with React Native and powered by Amazon Bedrock. With its minimalist design philosophy and robust privacy protection, it delivers real-time streaming conversations and AI image generation capabilities across Android, iOS, and macOS platforms. Check out the README for plenty of in depth details including sample screenshots from mobile simulators. Essential for any Swift developer (paging Seb!)

**amazon-bedrock-serverless-prompt-chaining**

[amazon-bedrock-serverless-prompt-chaining](https://aws-oss.beachgeek.co.uk/47w) is an essential resource for AWS developers keen to discover examples of how to build complex, serverless, and highly scalable generative AI applications with prompt chaining and Amazon Bedrock.

### AWS and Community blog posts

**This weeks essential reading**

Here are the posts that I think are essential reads, so start here.

* [AWS CDK is splitting Construct Library and CLI](https://aws-oss.beachgeek.co.uk/46b) - starting February 2025, the CDK CLI and the CDK Construct Library will no longer be released in lockstep and they will both have their own independent release cadence, meaning their version numbers are going to diverge - check out the post for additional details and the thinking behind this
* [Shaping the future of CDK together](https://aws-oss.beachgeek.co.uk/46c) - in more CDK news, make sure you check out this announcement around a new Contributor Council for CDK that is being formed - check the post but also see the video below, which was a recording of the first meeting
* [New Amazon S3 Tables: Storage optimized for analytics workloads](https://aws-oss.beachgeek.co.uk/46d) - provides everything you need to know about the re:Invent launch of Amazon S3 Tables, a new storage option optimised for tabular data using the Apache Iceberg format

**Community round up**

Each week I spent a lot of time reading posts from across the AWS community on open source topics. In this section I share what personally caught my eye and interest, and I hope that many of you will also find them interesting.

AWS Community Builder David Krohn starts us off with his post on unit and integration testing when using CDK, and specifically details around what the key differences are and when you might want to consider one versus the other. Read on in the post, [Enhancing Your AWS CDK Projects with Testing](https://aws-oss.beachgeek.co.uk/477). AWS Commuity Builder Matsuda follows up with more AWS CDK content in the post, [ElastiCache Serverless: L2 CDK Construct Released in open-constructs](https://aws-oss.beachgeek.co.uk/478), outlining the work done on an L2 Construct for ElastiCache Serverless which you can find on open-constructs, making it easy to automate your Valkey deployments. Sticking with Valkey we have Asaf Porat Stoler and Adar Guma Ovadya who put together [Reducing application latency and lowering Cloud bill by setting up your client library](https://aws-oss.beachgeek.co.uk/479), that dives into Availability Zone (AZ) affinity routing mechanics, showing how it optimises your application's performance and cost using Valkey GLIDE (General Language Independent Driver for the Enterprise). The post also guides you (or should that be glides you....argh sorry!) through how to configure GLIDE to benefit from other key features. Very cool indeed.

Next up we have the Data on EKS team who have put together another great recipe that shows you how you can use the newly launched Amazon S3 Tables with Amazon EKS in the post, [S3 Tables with EKS](https://aws-oss.beachgeek.co.uk/47a). If you have not seen these before they are great, so make sure you check the other recipes out too. Sticking with Kubernetes and data we have AWS Community Builder James Maina who writes, [Getting started on MOCO, the MySQL Operator for Kubernetes Part 1](https://aws-oss.beachgeek.co.uk/47b) a robust, cloud-native solution designed to simplify the management of MySQL clusters in Kubernetes environments. This is the first time I have heard about this, so need to give it a try. Sticking with cloud native, we have AWS Community Builder Daniel Megyesi who shares a great post about some gotchas that you should be aware of when using Karpenter and assumptions around resources being scaled down in his post, [My PodDisruptionBudget bible to use with Karpenter and friends](https://aws-oss.beachgeek.co.uk/47d) - defo worth a read that one. One of the launches at re:Invent I was most excited about was the Amazon EKS Hybrid Nodes, so I was super happy to read [Leverage On-Premises Infrastructure in Amazon EKS Clusters with Amazon EKS Hybrid Nodes](https://aws-oss.beachgeek.co.uk/47e), from AWS Community Builder Ahmed Salem who provides a quick post with how to set this up. 

Finally, we have AWS Community Builder Johannes Konings who shares how you can spin up VSCode on EC2 in the post, [Run vs code on a private AWS ec2 instance without ssh (with AWS CDK examples)](https://aws-oss.beachgeek.co.uk/47c). I do this myself, so will give this code a go as my current solution uses CloudFormation which is great, but I love CDK so this feels like a no brainer to me.

**Cloud Native**

* [Streamline Kubernetes cluster management with new Amazon EKS Auto Mode](https://aws-oss.beachgeek.co.uk/46h) - the launch post for Amazon EKS Auto Mode, so check this out to find out more about what this is and what problems it helps you solve [hands on]
* [Getting started with Amazon EKS Auto Mode](https://aws-oss.beachgeek.co.uk/46k) - dives deeper into Amazon EKS Auto Mode, covering the high-level architecture of EKS Auto Mode and providing a walkthrough for deploying a highly available, auto-scaled, sample application with EKS Auto Mode [hands on]
* [Use your on-premises infrastructure in Amazon EKS clusters with Amazon EKS Hybrid Nodes](https://aws-oss.beachgeek.co.uk/46l) - details another great launch from re:Invent, which provides a new capability that allows you to attach your on-premises and edge infrastructure as nodes to your Amazon EKS clusters [hands on]

![overview of eks hybrid node architecture](https://d2908q01vomqb2.cloudfront.net/da4b9237bacccdf19c0760cab7aec4a8359010b0/2024/11/24/2024-eks-hybrid-nodes-1-diagram.png)

* [Configuring ROSA for fine-grained ECR repository access](https://aws-oss.beachgeek.co.uk/46g) - demonstrates how to use Red Hat OpenShift Service on AWS (ROSA)  with Amazon Elastic Container Registry (ECR) and AWS Identity and Access Management (IAM) to protect access to your container images on a pod, namespace, node, or cluster level [hands on]
* [Announcing Bottlerocket FIPS variants](https://aws-oss.beachgeek.co.uk/46i) - dips into the news that Bottlerocket AMIs are now available that are pre-configured to use FIPS 140-3 validated cryptographic modules, so dive in if you want to find out more
* [Migrating from x86 to AWS Graviton on Amazon EKS using Karpenter](https://aws-oss.beachgeek.co.uk/46j) - provides an overview of strategies and best practices for migrating your cloud native application to AWS Graviton [hands on]
* [Scaling your LLM inference workloads: multi-node deployment with TensorRT-LLM and Triton on Amazon EKS](https://aws-oss.beachgeek.co.uk/46m)  - demonstrates how to create an EKS cluster optimised for multi-node inference using low-latency EFA networking, high-throughput EFS storage, and high-performance NVLink connected H100 GPU based P5.48xlarge instances [hands on]

![Detailed view of the architecture of the Llama3.1-405B model partitioned across p5.48xlarge nodes using LeaderWorkerSet](https://d2908q01vomqb2.cloudfront.net/e6c3dd630428fd54834172b8fd2735fed9416da4/2024/11/26/IMG-2024-11-26-11.25.34.png)

**Data and Analytics**

* [Automate pre-checks for your Amazon RDS for MySQL major version upgrade](https://aws-oss.beachgeek.co.uk/46p) - provides a custom solution that automates part of the Amazon RDS for MySQL upgrade pre-checks applicable to MySQL major versions 8.0 and 8.4, invoking the MySQL Shell upgrade checker utility on the selected Amazon RDS for MySQL instances and uploading the pre-checker log files to Amazon S3 for each instance [hands on]
* [Querying and writing to MySQL and MariaDB from Amazon Aurora and Amazon RDS for PostgreSQL using the mysql_fdw extension, Part 2: Handling foreign objects](https://aws-oss.beachgeek.co.uk/46s) - is the follow up post that shares how PostgreSQL foreign data wrappers provide a solution using mysql_fdw that enables you to connect to and query MySQL databases as if they were local tables from PostgreSQL databases [hands on]
* [Prevent transaction ID wraparound by using postgres_get_av_diag() for monitoring autovacuum](https://aws-oss.beachgeek.co.uk/46t) -  introduces postgres_get_av_diag(), a new function available in RDS for PostgreSQL to monitor aggressive autovacuum blockers [hands on]
* [JSON serialization using Serde Rust crates in Amazon RDS for PostgreSQL](https://aws-oss.beachgeek.co.uk/46q)  - dives deep and explains how PGRX type mappings can help you access PostgreSQL built-in types when writing a PL/Rust function [hands on]
* [Dynamic data masking in Amazon RDS for PostgreSQL, Amazon Aurora PostgreSQL, and Babelfish for Aurora PostgreSQL](https://aws-oss.beachgeek.co.uk/46r) - shows how you can implement dynamic data masking views in Aurora PostgreSQL-Compatible and Amazon RDS for PostgreSQL by generating masking views to mask the PII data for unauthorised users [hands on]

![end to end data masking process](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2024/12/20/ezatk-4243-pgddm-flow-1.png)

* [Improve Amazon Timestream for InfluxDB security posture by automating rotation for long-lived credentials](https://aws-oss.beachgeek.co.uk/46u) - walks you through how to make your Amazon Timestream for InfluxDB deployments more secure by offering a mechanism to automatically rotate long-lived credentials [hands on]
* [Automate topic provisioning and configuration using Terraform with Amazon MSK](https://aws-oss.beachgeek.co.uk/46o) - addresses some of the common challenges associated with manual MSK topic configuration management, using Terraform for automated topic provisioning and configuration [hands on]

* [Build a high-performance quant research platform with Apache Iceberg](https://aws-oss.beachgeek.co.uk/46v) - explores how Iceberg can enhance quant research platforms by improving query performance, reducing costs, and increasing productivity - by how much? read the post to find out [hands on]
* [How Amazon S3 Tables use compaction to improve query performance by up to 3 times](https://aws-oss.beachgeek.co.uk/473) -  studies the performance impact of compacting Parquet files using Amazon S3 Tables, and shares some interesting benchmarking stats - as always, you will have to dive into the post to see the numbers
* [Amazon EMR streamlines big data processing with simplified Amazon S3 Glacier access](https://aws-oss.beachgeek.co.uk/46w) - demonstrates how to set up and use Amazon EMR on EC2 with S3 Glacier for cost-effective data processing [hands on]
* [Amazon EMR 7.5 runtime for Apache Spark and Iceberg can run Spark workloads 3.6 times faster than Spark 3.5.3 and Iceberg 1.6.1](https://aws-oss.beachgeek.co.uk/46x) - makes some bold claims, but demonstrates the performance benefits of using the Amazon EMR 7.5 runtime for Spark and Iceberg using the TPC-DS 3TB benchmark v2.13 [hands on]
* [Run Apache Spark Structured Streaming jobs at scale on Amazon EMR Serverless](https://aws-oss.beachgeek.co.uk/46z) - highlights some of the key enhancements introduced for streaming jobs when using Apache Spark Structured Streaming [hands on]
* [Introducing AWS Glue 5.0 for Apache Spark](https://aws-oss.beachgeek.co.uk/470) - announced at re:Invent, this post shows you what’s new in AWS Glue 5.0, performance improvements, key highlights on Spark and related libraries, and how to get started [hands on]
* [Use open table format libraries on AWS Glue 5.0 for Apache Spark](https://aws-oss.beachgeek.co.uk/471) - dives deeper into the key upgrades on Iceberg, Delta Lake, and Hudi in AWS Glue 5.0 [hands on]
* [Read and write S3 Iceberg table using AWS Glue Iceberg Rest Catalog from Open Source Apache Spark](https://aws-oss.beachgeek.co.uk/472) - guides you through the seamless integration between Apache Spark and an AWS Glue Iceberg Rest Catalog for accessing Iceberg tables in Amazon S3 [hands on]
* [Building end-to-end data lineage for one-time and complex queries using Amazon Athena, Amazon Redshift, Amazon Neptune and dbt](https://aws-oss.beachgeek.co.uk/46y) - shares how dbt enables unified data modelling across Amazon Athena and Amazon Redshift, integrating data lineage from both one-time and complex queries [hands on]

![filtered results table from neptune](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2024/12/08/Figure-15-new-Filtered-results-based-on-title_crew-table-in-Neptune.png)

* [Announcing Amazon FSx Intelligent-Tiering, a new storage class for FSx for OpenZFS](https://aws-oss.beachgeek.co.uk/474) - was another announcement from re:Invent, sharing how you can now benefit from using a new storage tiering class when using OpenZFS, which should help you to reduce some of your storage costs [hands on]
* [From caching to real-time analytics: Essential use cases for Amazon ElastiCache for Valkey](https://aws-oss.beachgeek.co.uk/476) - explores some of the most common use cases of ElastiCache for Valkey, demonstrating how its unique capabilities enable faster, more scalable, and resilient applications [hands on]

**Other posts to check out**

* [AWS Amplify Hosting Adds Web Application Firewall Protection – Public Preview](https://aws-oss.beachgeek.co.uk/46e) - shares how AWS Amplify users can now take advantage of new Firewall capabilities that will allow developers to protect and further secure their web applications thanks to direct integration with AWS WAF - this will allow Amplify developers to connect a Web ACL directly to their Amplify hosted application
* [Connect users to data through your apps with Storage Browser for Amazon S3](https://aws-oss.beachgeek.co.uk/475) - walks you through how you can implement a new ui component in AWS Amplify that makes it super easy to provide a nice GUI over your S3 buckets [hands on]
* [Detect and respond to security threats in near real-time using Amazon Managed Grafana](https://aws-oss.beachgeek.co.uk/46f) - shows you how you can centralise your AWS Security Hub findings that provide a single-pane-of-glass on workloads running on AWS cloud, using Amazon Managed Grafana [hands on]

![overview of architecture](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2024/10/22/Figure1.png)

### Quick updates

**PostgreSQL**

Amazon Aurora PostgreSQL-Compatible Edition now supports PostgreSQL versions 16.6, 15.10, 14.15, 13.18, and 12.22. Please note, this release supports the versions released by the PostgreSQL community on November 21,2024 and not the previous November 14,2024 release. These releases contain product improvements and bug fixes made by the PostgreSQL community, along with Aurora-specific security and feature improvements such as improved read replica upgrades for reduced downtime, new features for Babelfish and improved Global Database cross-region resiliency for better read availability during unplanned events.

As a reminder, Amazon Aurora PostgreSQL 12 standard support ends on Feb 28, 2025. You can either upgrade to a newer major version or continue to run Amazon Aurora PostgreSQL 12 past the end of standard support date with RDS Extended Support.

**MariaDB**

Amazon Relational Database Service (Amazon RDS) for MariaDB now supports MariaDB minor versions 11.4.4, 10.11.10, 10.6.20, and 10.5.27. We recommend that you upgrade to the latest minor versions to fix known security vulnerabilities in prior versions of MariaDB, and to benefit from the bug fixes, performance improvements, and new functionality added by the MariaDB community. You can leverage automatic minor version upgrades to automatically upgrade your databases to more recent minor versions during scheduled maintenance windows. You can also leverage Amazon RDS Managed Blue/Green deployments for safer, simpler, and faster updates to your MariaDB instances.

If you are looking for newer releases, Amazon RDS for MariaDB now supports MariaDB Innovation Release 11.7 in the Amazon RDS Database Preview Environment, allowing you to evaluate the latest Innovation Release on Amazon RDS for MariaDB. You can deploy MariaDB 11.7 in the Amazon RDS Database Preview Environment that has the benefits of a fully managed database, making it simpler to set up, operate, and monitor databases. MariaDB 11.7 is the latest Innovation Release from the MariaDB community, and includes support for vector datatype, indexing, and search capabilities. MariaDB Innovation releases are supported by the community until the next Innovation release, whereas MariaDB Long Term Maintenance Releases, such as MariaDB 10.11 and MariaDB 11.4, are supported by the community for up to five years. Please refer to the MariaDB 11.7 release notes for more details about this release.

The Amazon RDS Database Preview Environment supports both Single-AZ and Multi-AZ deployments on the latest generation of instance classes. Amazon RDS Database Preview Environment database instances are retained for a maximum period of 60 days and are automatically deleted after the retention period. Amazon RDS database snapshots that are created in the preview environment can only be used to create or restore database instances within the preview environment.

**Apache Kafka**

Amazon Managed Streaming for Apache Kafka Connect (Amazon MSK Connect) now supports Apache Kafka Connect version 3.7 for new connectors. Apache Kafka Connect version 3.7 includes several bug fixes and performance improvements. For more details and a complete list of improvements and bug fixes, see the Apache Kafka release notes for version 3.7.

In more news, Amazon MSK Connect now supports updating connector configuration of existing connectors. With this launch, you can change the configuration of your connector using a single, UpdateConnector API call. You can make changes to your connector settings, such as updating source or sink destinations, or processing configurations. Amazon MSK Connect allows you to deploy and operate Apache Kafka Connect connectors in a fully managed environment. You can modify the connector configuration parameters of your existing connector when you have changes in your source or sink settings such as source database tables or topics to deliver to S3 bucket. You can update the connector configuration using the Amazon MSK Console, AWS CLI, SDK, or CloudFormation. After you update the connector, you can also check the update operation status in the MSK console or using API.

**Kubernetes**

Amazon Elastic Kubernetes Service (EKS) now lets you programmatically access availability of Kubernetes versions. This simplifies how you can discover and select available versions before creating or upgrading clusters.

Kubernetes evolves rapidly, introducing three minor version releases each year with new features, design updates, and bug fixes. EKS provides standard support for each minor version for 14 months after release. After standard support ends, the version enters a 12-month extended support period. EKS stops supporting Kubernetes versions 26 months after their release. With this launch, you can now programmatically retrieve Kubernetes version metadata, including support status and dates. You can also discover the EKS platform version and default Kubernetes version EKS will use when creating new clusters.

### Videos of the week

**CDK Contributor Council Charter RFC**

If you were not aware, changes are afoot with the AWS CDK community. This short video walks through a recent presentation of the CDK Contributor Council Charter which aims to improve the visibility into CDK, increase feedback opportunities, all with the aim of building a stronger and more inclusive community. If you have contributed to CDK in the past, or have been thinking about it, then this is essential viewing.

{{< youtube 5BXynfEJHts >}}

**Querying S3 Tables with Spark on Kubernetes and DuckDB**

Open source hero Damon Cortesi has put together a video that shows how you can create and query Amazon S3 Tables with Spark on Kubernetes. Check out the comments where you can find a link to supporting GitHub repos.

{{< youtube LK_-OzwlqYw >}}

**re:Invent 2024 open source sessions**

I have collected as many of the sessions that were recorded and published below, so if you missed re:Invent or want to catch up, check out these sessions.

*OPN201	OpenSearch: A journey from fork to Linux Foundation*

{{< youtube w0KfmeiXIvE >}}

*OPN202	Managing infrastructure via APIs with AWS Controllers for Kubernetes*
	
{{< youtube lCL_zOUSM-s >}}

*OPN311	Harnessing Apache ActiveMQ: ActiveMQ 6.x features and roadmap*

{{< youtube Jwgq7Hs687k >}}

*OPN312	Infrastructure as Kubernetes APIs*

{{< youtube PDb9nLsjFzY >}}

*OPN402	Gain expert-level knowledge about Powertools for AWS Lambda*

{{< youtube kxJTq8FTkDA >}}

*OPN405	Elevating the developer experience with Backstage on AWS*

{{< youtube 0eGaa7EQkxM >}}

*OPN406	Handle millions of observability events with Apache Flink & Prometheus*

{{< youtube trhsC9tcGU4 >}}

**Cedar on Amazon EKS**

Joining Sai Vennam on the Containers Couch is Micah Hausler who has been working on a really cool open source project called **cedar-access-control-for-k8s** (featured in the projects section above). After a quick introduction to Cedar, Micah explains the basics of Cedar and goes through examples of what sets Cedar apart from RBAC and Kubernetes policy engines. Essential viewing folks.

{{< youtube xtLpBPYJlzU >}}


### Events for your diary

If you are planning any events in 2024, either virtual, in person, or hybrid, get in touch as I would love to share details of your event with readers. 

**FOSDEM**
**February 1st/2nd, Brussels University**

[FOSDEM](https://fosdem.org/2025/) is back again, taking place at the University of Brusels over the weekend of the 1st and 2nd. I will be there on the Saturday manning the Data Analytics dev room, so hope to see some of you there. There are of course hundreds of other amazing talks and tracks, so if you can, make sure you put this on your diary. The event is free, and transport and accommodation in Brussels is very reasonable, so start 2025 by attending this event.


**State of Open Source**
**February 4th and 5th, Sancroft, Rose St, Paternoster Sq., St Paul's London EC4M 7DQ**

Back again with an even more stellar line up than last year, the essential open source event for folks living in the UK. Check out the line up and register (very reasonable) [here](https://stateofopencon.com/)

**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://aws-oss.beachgeek.co.uk/1az)

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes: Vlad Holubiev, Damon Cortesi, Ivica Kolenkaš, Manuel Vogel, Denis Traub, Victor Omolayo, Aidan Steele, Rishi Kavikondala, Danilo Poccia, Niko Virtala, Samuel Cochran, Rico Huijbers, Hannah Aubry, Jeff Barr, Nikhil Swaminathan, Sameeksha Garg, Anjali Sharma, Scott Kellish, Yash Bindlish, Steve Mirman,  Channy Yun (윤석찬) , Johannes Brück, Donald Dragoti, Steve Flinchbaugh, Maximilian Schellhorn, Dionysios Kakaletris, Alex Kestner, Ashley Ansari, Robert Northard, Sheetal Joshi, Aman Shanbhag, Jiahong Liu, Kshitiz Gupta, Rohan Varma, Wenhan Tan, Vijay Kardile, Cade Kettner, Nirupam Datta, Pat Doherty, Ryan Moore, Michael You, Ezat Karimi, Kumar Babu P G, Rohit Kapoor, Naga Appani, Forest Vey, Guy Bachar, Alex Tarasov, Boris Litvin, Jiwan Panjiker, Sercan Karaoglu, Salim Tutuncu, Giovanni Matteo Fumarola, Narayanan Venkateswaran, Karthik Prabhakar, Atul Payapilly, Udit Mehrotra, Nancy Wu, Xu Feng, Da Xu, Anubhav Awasthi, Kshitija Dound, Paul Min, Noritaka Sekiyama, Maheedhar Reddy Chappidi, Stuti Deshpande, Rajendra Gujja, Matt Su, Mohit Saxena, Kartik Panjabi, Anshul Sharma, Savio Dsouza, Martin Ma, Sotaro Hikita, Raj Ramasubbu, Pratik Das, Srividya Parthasarathy, Aliaa Abbas, Anupriti Warade, Jacob Tardieu, Siva Karuturi, David Krohn, Matsuda , Johannes Konings,  Ahmed Salem, Daniel Megyesi, James Maina, Asaf Porat Stoler and Adar Guma Ovadya.

**Feedback**

Please please please take 1 minute to [complete this short survey](https://www.pulse.aws/promotion/10NT4XZQ). 

### Stay in touch with open source at AWS

Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) for more open source goodness.

One of the pieces of feedback I received in 2023 was to create a repo where all the projects featured in this newsletter are listed. Where I can hear you all ask? Well as you ask so nicely, you can meander over to[ newsletter-oss-projects](https://aws-oss.beachgeek.co.uk/3l8).

Made with ♥ from DevRel
