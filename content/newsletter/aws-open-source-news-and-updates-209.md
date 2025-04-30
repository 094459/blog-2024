---
title: 'AWS open source newsletter #209'
date: '2025-04-29'
tags : [ oss-newsletter, aws open source, Ruby, Apache Airflow, MWAA, Amazon EKS, Kubernetes, Bottlerocket, Karpenter, PostgreSQL, Apache Iceberg, Apache OFBiz, Apache Flink, Prometheus, Grafana, AWS Amplify, Spring Boot, LangChain, Valkey, LangGraph, MLFlow, AuthZen, Amazon Corretto, AWS CDK, Apache Kafka, memecachd, AWS ParallelCluster, Amazon Linux, Swift  ]
canonicalUrl: "https://dev.to/aws/aws-open-source-newsletter-209-39mo"
---

##  Edition #209 - April 2025

Welcome to issue #209 of the AWS open source newsletter, the newsletter where we try and provide you the best open source on AWS content. I am publishing this from the AWS Summit London, and it has been great to speak to so many of the AWS community about open source - it is very much alive and thriving, so thank you all!

As always, in this edition we have more great new projects to check out, which include a bumper selection of the current hot topic that is Model Context Protocol (MCP). We also have a collection of security related projects too, which is great to see. Other projects include tools to help you migrate your S3 buckets, a very nice profiler for AWS Step Function users, a nice example solution for getting ollama up and running on AWS, and a generative AI powered tool that help you create AWS deployable solutions from chat or diagrams. 

The projects will keep you busy until next month for sure, but we also have plenty of reading material in this months newsletter. In this edition we have featured projects that include Ruby, Apache Airflow, Kubernetes, Bottlerocket, Karpenter, PostgreSQL, Apache Iceberg, Apache OFBiz, Apache Flink, Prometheus, Grafana, AWS Amplify, Spring Boot, LangChain, Valkey, LangGraph, MLFlow, AuthZen, Amazon Corretto, AWS CDK, Apache Kafka, memecachd, AWS ParallelCluster, Amazon Linux, and Swift.

As always, get in touch if you want me to feature your projects in this open source newsletter. Until the next time, I will leave you to dive into the good stuff!

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution. The projects mentioned here do not represent any formal recommendation or endorsement, I am just sharing for greater awareness as I think they look useful and interesting!*

### Tools

**mcp**

[mcp](https://aws-oss.beachgeek.co.uk/4bi) is a comprehensive repo that provides a suite of specialised Model Context Protocol (MCP) servers that help you get the most out of AWS, wherever you use MCP. This list is growing, so check out the list (currently contains MCP servers that will help you with AWS documentation, AWS Cost Analysis, using AWS CDK, and more).

**middy-mcp**

[middy-mcp](https://aws-oss.beachgeek.co.uk/4bk) provides [Middy](https://github.com/middyjs/middy) [middleware](https://middy.js.org/)  (a Node.js middleware engine for AWS Lambda that helps you organise your Lambda code, remove code duplication, and focus on business logic) for Model Context Protocol (MCP) server integration with AWS Lambda functions. It provides a convenient way to handle MCP requests and responses within your Lambda functions using the Middy middleware framework. It supports requests sent to AWS Lambda from API Gateway (both REST API / v1 and HTTP API / v2) using the Proxy integration, as well as requests sent form an ALB. Check out the README for some code examples of how you might use this.

**Log-Analyzer-with-MCP**

[Log-Analyzer-with-MCP](https://aws-oss.beachgeek.co.uk/4bu) - this repo provides a Model Context Protocol (MCP) server that provides AI assistants access to AWS CloudWatch Logs for analysis, searching, and correlation. The README provides everything you need to get started, as well as providing links that dive deeper into how this works.

**s3-migrate**

[s3-migrate](https://aws-oss.beachgeek.co.uk/4bh) is a project that came onto my radar thanks to a message from Luciano Mammino, and provides a command line tool to help you move all your objects between s3-compatible storage systems. It can migrate objects from one S3-compatible storage bucket to another, resuming interrupted transfers using a SQLite state file. This project is (currently) experimental so use with care, and is intended for a one-off migration, not to keep two buckets in sync. Check out the README for more details on how to configure and use this tool. 

**sfn-profiler**

[sfn-profiler ](https://aws-oss.beachgeek.co.uk/4bn)is a nice project from James Sanders that provides a package of utilities for profiling AWS Step Function executions. This utility provides relevant performance metrics and information about particular Step Function executions and their child workflows (called 'contributor' workflows) in your local web browser. It displays information such as the largest contributors to the overall duration as well as a gantt chart representation of the workflow execution. Check out the README for more details, this really is an essential tool if you spend any time at all developing AWS Step Functions.

![example step function being profiled](https://raw.githubusercontent.com/sanjams2/sfn-profiler/refs/heads/main/docs/example.png)

**sample-devgenius-aws-solution-builder**

[sample-devgenius-aws-solution-builder](https://aws-oss.beachgeek.co.uk/4bx) is a super interesting project that you can deploy and provides an AI-powered application that transforms project ideas into complete, ready-to-deploy AWS solutions. It leverages Amazon Bedrock and Claude AI models to provide architecture diagrams, cost estimates, infrastructure as code, and comprehensive technical documentation. In "Conversational Solution Architecture Building" mode,  DevGenius enables customers to design solution architectures in a conversational manner. Users can create architecture diagrams (in draw.io format) and refine them interactively. Once the design is finalised, they can generate end-to-end code automation using CDK or CloudFormation templates, and deploy it in their AWS account with a single click. Additionally, customers can receive cost estimates for running the architecture in production, along with detailed documentation for the solution. In the "Build Solution Architecture from Whiteboard Drawings" mode, those of you who already have their architecture in image form (e.g., whiteboard drawings), DevGenius allows you to upload the image. Once uploaded, DevGenius analyses the architecture and provides a detailed explanation. You can then refine the design conversationally and, once finalised, generate end-to-end code automation using CDK or CloudFormation. Cost estimates and comprehensive documentation are also available.

I have not tried it yet, but it looks super interesting so go check it out.

![demo of devgenius in action](https://github.com/aws-samples/sample-devgenius-aws-solution-builder/blob/main/demo/DevGenius_Demo.gif?raw=true)

**ai-on-eks**

[ai-on-eks](https://aws-oss.beachgeek.co.uk/4bw) is your go to repo if you are interested in getting AI up and running on Amazon EKS. It provides a gateway to help you scale AI and ML workloads on Amazon EKS. It provides a rich collection of Terraform Blueprints featuring current good practices for deploying robust solutions with advanced logging and observability. You can explore practical patterns for running AI/ML workloads on EKS, leveraging the power of the Ray ecosystem for distributed computing. Utilise advanced serving solutions like NVIDIA Triton Server, vLLM for efficient and scalable model inference, and TensorRT-LLM for optimising deep learning models.

**dAWShund**

[dAWShund](https://aws-oss.beachgeek.co.uk/4bj) is a suite of tools to enumerate, evaluate and visualise the access conditions between different resources in your AWS environments. Perhaps the most critical component of an AWS infrastructure is the policy document describing the actions allowed or denied to a resource. This can get overwhelming sometimes, so tools like this will provide you with the help you need to keep on top of it. Check out the README for details on usage.

**cloud-snitch**

[cloud-snitch](https://aws-oss.beachgeek.co.uk/4bo) - is an essential learning tool for anyone using AWS that helps you better understand  your AWS account activity. Inspired by the MacOS tool "Little Snitch", this will visually show you your AWS activity, allow you to share and collaborate with others, summarise your AWS activity through a number of different lenses and help you uncover suspicious behaviour. You have to check out the README to get a look at some of the screenshots of this tool in use, looks super interesting.

**OpenSecOps-Org**

[OpenSecOps-Org](https://aws-oss.beachgeek.co.uk/4bq) is the repo that holds the various sub projects that are part of [opensecops.org](https://www.opensecops.org/), that provide open source tools and solutions that help you seamlessly integrate into your operations, providing robust security frameworks and operational excellence. I have not actually looked at this in detail, but just skimming it looks very comprehensive. Split across Foundation that helps you setup your AWS against industry standard good practices, and Soar that looks more at continuous monitoring, automated incident handling and remediation of security issues.

**kye**

[kye](https://aws-oss.beachgeek.co.uk/4br), also known as "Know Your Enemy", is a tool that analyses IAM Role trust policies and S3 bucket policies in your AWS account to identify third-party vendors with access to your resources. It compares the AWS account IDs found in these policies against a reference list of known AWS accounts from fwd:cloudsec to identify the vendors behind these accounts. Simple to install, the README provides example configurations and instructions on how to get started.

**ww-project-eks-goat**

[www-project-eks-goat](https://aws-oss.beachgeek.co.uk/4bp) this repo provides an immersive workshop on AWS ECR & EKS Security designed to take participants through real-world scenarios of attacking and defending Kubernetes clusters hosted on AWS EKS. This workshop provides a comprehensive approach, from understanding the anatomy of attacks on EKS clusters using AWS ECR to deploying robust defense mechanisms. Participants will learn how to backdoor AWS ECR image & exploit misconfigurations and vulnerabilities within AWS EKS, followed by the implementation of best security practices to safeguard the environment.

This workshop is tailored for security professionals, cloud engineers, and DevOps teams looking to enhance their understanding of offensive and defensive Kubernetes security strategies.

**cdk-project-rules**

[cdk-project-rules](https://aws-oss.beachgeek.co.uk/4bs) is a new repo from AWS Community Builder Christian Benzolet that provides a collection of versioned project rules to enhance CDK application development with Amazon Q Developer. By providing a set of standardised project rules that can be used with Amazon Q Developer, this will help improve the development experience when working with AWS Cloud Development Kit (CDK). These rules help developers follow best practices, maintain consistency, and accelerate development of CDK applications. The project is currently looking for contributions, so if you are using CDK and been experimenting successfully with Amazon Q Developer, take a look.

### Demos, Samples, Solutions and Workshops

**Lambda-MCP-Server**

[Lambda-MCP-Server](https://aws-oss.beachgeek.co.uk/4bl) - this project from my colleague Mike Chambers demonstrates a powerful and developer-friendly way to create serverless MCP (Model Context Protocol) tools using AWS Lambda. It showcases how to build a stateless, serverless MCP server with minimal boilerplate and an excellent developer experience. The included client demonstrates integration with Amazon Bedrock, using the Bedrock Converse API and Amazon Nova Pro to build an intelligent agent.

**sample-agents-with-nova-act-and-mcp**

[sample-agents-with-nova-act-and-mcp](https://aws-oss.beachgeek.co.uk/4bm) - This repository demonstrates how to build intelligent web automation agents using Amazon Nova Act integrated with MCP (Model Context Protocol). MCP provides a standardised way to connect AI models to different data sources and tools - think of it like a "USB-C port for AI applications." The repo provides requirements for running these demos as well as an overview of the different example use cases.

**Sample-Model-Context-Protocol-Demos**

[Sample-Model-Context-Protocol-Demos](https://aws-oss.beachgeek.co.uk/4bt) - this repo provides a list of examples of how to use Model Context Protocol (MCP) with AWS. Keep an eye on this repo as it will grow as MCP is the new hotness at the moment.

**sample-ollama-server**

[sample-ollama-server](https://aws-oss.beachgeek.co.uk/4bv) is a project that folks who are interested in or already using ollama need to check out. This repo provides a AWS CloudFormation template to provision NVIDIA GPU EC2 instances with Ollama and Open WebUI, and include access to Amazon Bedrock foundation models (FMs). The solution can be deployed as a website for LLM interaction through Open WebUI, or as application development environment with Amazon DCV server.

![screenshot of ollama running via dcv](https://github.com/aws-samples/sample-ollama-server/blob/main/images/ollama-dcv.png?raw=true)

### AWS and Community blog posts

**This weeks essential reading**

Here are the posts that I think are essential reads, so start here.

* [Announcing the Developer Preview of Amazon S3 Transfer Manager in Rust](https://aws-oss.beachgeek.co.uk/4bg) - looks at a new Rust based high-level utility that speeds up and simplifies uploads and downloads with Amazon Simple Storage Service (Amazon S3) [hands on]
* [AWS Cloud Credits for Open Source Projects: Affirming Our Commitment](https://aws-oss.beachgeek.co.uk/4b1) - is a must read that shares some of the ways that we are supporting open source, including reaffirming our commitment to providing vital infrastructure for free and open source software projects - make sure you also read to understand the updated eligibility and application requirements for our AWS Cloud Credits for Open Source program
* [AWS SDK for Ruby: Deprecating Ruby 2.5 & 2.6 Runtime Supports and Future Compatibility](https://aws-oss.beachgeek.co.uk/4b3) - provides essential updates and key dates for those of you using the AWS SDK for Ruby
* [Build unified pipelines spanning multiple AWS accounts and Regions with Amazon MWAA](https://aws-oss.beachgeek.co.uk/4ay) - demonstrate how to use Amazon MWAA for centralised orchestration, while distributing data processing and machine learning tasks across different AWS accounts and Regions for optimal performance and compliance [hands on]
* [Under the hood: Amazon EKS Auto Mode](https://aws-oss.beachgeek.co.uk/4b7) - peeks under the hood to provide a deeper understanding of what makes Amazon EKS Auto Mode tick

![amazon eks auto mode responsibility model](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2025/03/31/Picture4-6.jpg)

**Cloud Native**

* [Amazon EKS introduces node monitoring and auto repair capabilities](https://aws-oss.beachgeek.co.uk/4au) - walks you through how Amazon EKS node monitoring and auto repair offers a major improvement in Kubernetes operations by automatically detecting and addressing node failures that can impact workload availability [hands on]
* [Announcing Amazon EKS community Add-ons catalog](https://aws-oss.beachgeek.co.uk/4b6) - dives deep into community add-ons catalog, which provides a way to streamline cluster operations by integrating popular community add-ons through native AWS management, broadening the choice of add-ons that users can install to their cluster directly using Amazon EKS console, AWS software development kit (SDK), AWS Command Line Interface (AWS CLI), or infrastructure as code (IaC) tools such as AWS CloudFormation [hands on]
* [Modernizing Snowflake Corporate’s Kubernetes Infrastructure with Bottlerocket and Karpenter](https://aws-oss.beachgeek.co.uk/4b8) - provides a nice case study on Snowflake's corporate Kubernetes infrastructure migration to Bottlerocket and Karpenter

**Data and Analytics**

* [Improve PostgreSQL performance using the pgstattuple extension](https://aws-oss.beachgeek.co.uk/4bd) - looks at how you can use this plugin to help you diagnose and improve performance impacting issues [hands on]
* [Best practices to handle AWS DMS tasks during PostgreSQL upgrades](https://aws-oss.beachgeek.co.uk/4av) - is a must read if you plan on using AWS Database Migration Service (DMS) to help you upgrade your PostgreSQL databases, providing some good current practices when upgrading to minor or major versions [hands on]
* [Read and write Apache Iceberg tables using AWS Lake Formation hybrid access mode](https://aws-oss.beachgeek.co.uk/4az) - provides a detailed solution that shows you how to scale the adoption and use of Iceberg tables using Lake Formation permissions for read workloads, while maintaining full control over table schema and data updates through IAM policy-based permissions for the table owner [hand on]
* [Manage concurrent write conflicts in Apache Iceberg on the AWS Glue Data Catalog](https://aws-oss.beachgeek.co.uk/4bb) - demonstrates how to implement reliable concurrent write handling mechanisms in Iceberg tables, exploring Iceberg’s concurrency model, examining common conflict scenarios, and providing practical implementation patterns of both automatic retry mechanisms and situations requiring custom conflict resolution logic for building resilient data pipelines [hands on]

![apache iceberg conflict resolution workflow](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2025/04/02/BDB-5015-2.jpg)

* [Process millions of observability events with Apache Flink and write directly to Prometheus](https://aws-oss.beachgeek.co.uk/4ba) - explains how the new Apache Flink connector for Prometheus works, showing how you can manage your Prometheus metrics data cardinality by preprocessing raw data with Flink to build real-time observability with Amazon Managed Service for Prometheus and Amazon Managed Grafana [hands on]
* [Up and running with Apache OFBiz and Amazon Aurora DSQL](https://aws-oss.beachgeek.co.uk/4be) - looks at how you can run complex applications (in this case, Apache OFBiz) on Amazon Aurora DSQL, exploring the various changes and minor updates you might need to make when looking at your own applications.

**Other posts to check out**

* [Firewall support for AWS Amplify hosted sites](https://aws-oss.beachgeek.co.uk/4bf) - is the general announcement post that AWS WAF is now integrated with AWS Amplify Hosting [hands on]
* [Integrate your Spring Boot application with Amazon ElastiCache](https://aws-oss.beachgeek.co.uk/4aw) - explores the basics of integrating a Spring Boot application with ElastiCache to enable caching [hands on]
* [Advanced tracing and evaluation of generative AI agents using LangChain and Amazon SageMaker AI MLFlow](https://aws-oss.beachgeek.co.uk/4bc) - shows you how to combine LangChain’s LangGraph, Amazon SageMaker AI, and MLflow to demonstrate a powerful workflow for developing, evaluating, and deploying sophisticated generative AI agents [hands on]
* [Build multi-agent systems with LangGraph and Amazon Bedrock](https://aws-oss.beachgeek.co.uk/4ax) - demonstrates how to integrate the open source multi-agent framework LangGraph, with Amazon Bedrock  to build powerful, interactive multi-agent applications that use graph-based orchestration [hands on]

![supervisor agent with complete workflow](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2025/04/03/ml-18369-image6.png)

* [Port .NET Framework workloads to Linux with Amazon Q Developer, Part 3: Web APIs](https://aws-oss.beachgeek.co.uk/4b4) - is the next in a series of posts that helps you modernise .NET workloads and move them onto open source alternatives
* [How to support OpenID AuthZEN requests with Amazon Verified Permissions](https://aws-oss.beachgeek.co.uk/4b9) - introduces an open source AuthZEN interface for Amazon Verified Permissions that’s based on the OpenID Foundation’s AuthZEN working group specifications, that provides developers with a transparent way to adopt industry-standard authorisation practices while maintaining the security and scalability benefits of the managed authorisation service provided by AWS [hands on]

![architecture overview](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2025/04/01/Figure-2.png)

### Quick updates

**Amazon Corretto**

Amazon announces quarterly security and critical updates for Amazon Corretto Long-Term Supported (LTS) and Feature Release (FR) versions of OpenJDK. Corretto 24.0.1, 21.0.7, 17.0.15, 11.0.27, 8u452 are now available for download. Amazon Corretto is a no-cost, multi-platform, production-ready distribution of OpenJDK. Go check the [home page](https://aws.amazon.com/corretto/?filtered-posts.sort-by=item.additionalFields.createdDate&filtered-posts.sort-order=desc&trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) to download version 8, 11, 17, 21, or 24.

**AWS CDK**

Amazon Web Services (AWS) announces the general availability of a couple of AWS Cloud Development Kit (AWS CDK) L2 constructs:

First up is the library for Amazon EventBridge Scheduler. This construct library allows developers to programmatically create, configure, and manage scheduled tasks using infrastructure as code with their preferred programming language, simplifying the process of building event-driven applications. The EventBridge Scheduler construct library enables you to define schedules using cron or rate expressions, configure target destinations including AWS Lambda functions, Amazon SQS queues, and other AWS services, and manage execution windows and retry policies. Developers can now leverage type-safe programming languages to define their scheduling infrastructure, improving code maintainability and reducing configuration errors.

Second up is the construct for Amazon Cognito Identity Pools. This library enables developers to programmatically define and deploy Identity Pool resources using familiar programming languages, making it easier to grant users secure access to AWS services in their applications. With this construct library, you can define Identity Pools as infrastructure as code, configure authentication providers like Amazon Cognito User Pools, social identity providers (Facebook, Google, Apple, Amazon), and SAML 2.0 providers. The library helps you implement security best practices by default and reduces the complexity of managing authentication and authorisation for your web and mobile applications.

Check out the post from Adam Keller that dives deeper into this, [Announcing the AWS CDK L2 Construct for Amazon Cognito Identity Pools](https://aws-oss.beachgeek.co.uk/4b0)

**PostgreSQL**

In this months roundup, we have quite a few updates for PostgreSQL fans.

Amazon Aurora PostgreSQL-Compatible Edition now supports PostgreSQL versions 16.8, 15.12, 14.17 and 13.20. Please note, this release supports the versions released by the PostgreSQL community on February 20,2025 which replaces the previous February 13, 2025 release. These releases contain product improvements and bug fixes made by the PostgreSQL community, along with Aurora-specific security and feature improvements such as dynamic resizing of the allocated space for Optimized Reads-enabled temporary objects on Aurora I/O-Optimized clusters and new features for Babelfish. For more details, please refer to the [release notes](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraPostgreSQLReleaseNotes/AuroraPostgreSQL.Updates.html?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el).

Amazon Aurora PostgreSQL-Compatible Edition now supports pgvector 0.8.0, an open-source extension for PostgreSQL for storing vector embeddings in your database. pgvector provides vector similarity search capabilities that enables Aurora use in generative artificial intelligence (AI) semantic search and retrieval-augemented generation (RAG) applications. pgvector 0.8.0 includes improvements to PostgreSQL query planner’s selection of index when filters are present, which can deliver better query performance and improve search result quality. pgvector 0.8.0 improves data filtering using conditions in WHERE clauses and joins that can improve query performance and usability. Additionally, the [iterative index scans](https://github.com/pgvector/pgvector?tab=readme-ov-file#iterative-index-scans) help prevent ‘overfiltering’, ensuring generation of sufficient results to satisfy the conditions of a query. If an initial index scan doesn't satisfy the query conditions, pgvector will continue to search the index until it hits a configurable threshold. pgvector 0.8.0 also has performance improvements for searching and building [HNSW](https://github.com/pgvector/pgvector?tab=readme-ov-file#hnsw) indexes. pgvector 0.8.0 is available in Amazon Aurora clusters running PostgreSQL 16.8, 15.12, 14.17, and 13.20 and higher in all AWS Regions including AWS GovCloud (US) Regions, except China. You can initiate a minor version upgrade by modifying your DB cluster. Please [review the Aurora documentation](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/USER_UpgradeDBInstance.PostgreSQL.html?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) to learn more.

Following that is news that Amazon Relational Database Service (RDS) for PostgreSQL now supports modifying the ssl_ciphers parameter. SSL Ciphers (or cipher suites) are combinations of algorithms used to secure network connections between a client and server. They handle key exchange, authentication, encryption, and message integrity verification to ensure secure and confidential communication. Amazon RDS for PostgreSQL 16.1 and later will support modification of the ssl_ciphers parameter. You can select cipher suites from the Amazon RDS for PostgreSQL [allow list](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/PostgreSQL.Concepts.General.SSL.html#PostgreSQL.Concepts.General.SSL.Ciphers?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) to align with your organisation's security standards and maintain consistent security configurations across database deployments.

Next up is an update for those of you using Amazon RDS Proxy with PostgreSQL. Amazon RDS Proxy now supports version 1.3 of the Transport Layer Security (TLS) protocol for Proxy connections to Amazon Aurora PostgreSQL and RDS for PostgreSQL database instances. TLS 1.3 provides improved security through stronger cryptographic algorithms and simplified handshake process as compared to older TLS versions. With this release, RDS Proxy can use TLS 1.3 for connections to Aurora PostgreSQL and RDS for PostgreSQL databases. During connection establishment, Proxy will automatically negotiate the most secure supported TLS version supported with the database. Customers can also configure their PostgreSQL database to require TLS 1.3, by setting the ssl_min_protocol_version parameter in their parameter group. TLS 1.3 is already supported for connections to RDS Proxy, as well as for RDS Proxy connections to MySQL engines.

Finally, and important if you are running older versions of PostgreSQL, is news that Amazon RDS for PostgreSQL announced Amazon RDS Extended Support minor version 11.22-rds.20250220 and 12.22-rds.20250220. We recommend that you upgrade to this version to fix known security vulnerabilities and bugs in prior versions of PostgreSQL. Amazon RDS Extended Support provides you more time, up to three years, to upgrade to a new major version to help you meet your business requirements. During Extended Support, Amazon RDS will provide critical security and bug fixes for your RDS for PostgreSQL databases after the community ends support for a major version. You can run your PostgreSQL databases on Amazon RDS with Extended Support for up to three years beyond a major version’s end of standard support date.

**Apache Kafka**

Amazon Managed Streaming for Apache Kafka (Amazon MSK) now supports Apache Kafka version 3.9, which allows users to retain tiered data when disabling Tiered Storage at the topic level. Consumer applications can continue to read historical data from the remote log start offset (Rx) while maintaining continuous log offsets across both local and remote storage.
Along with this feature, Apache Kafka version 3.9 includes various bug fixes and improvements. For more details, please refer to the [Apache Kafka release notes for version 3.9](https://downloads.apache.org/kafka/3.9.0/RELEASE_NOTES.html).

**Memcached**

Amazon ElastiCache has introduced the ability to perform vertical scaling on self-designed Memcached caches on ElastiCache. Amazon ElastiCache is a fully managed, Valkey-, Memcached- and Redis OSS-compatible service that delivers real-time, cost-optimised performance for modern applications with 99.99% availability. With this launch, you can now dynamically adjust the compute and memory resources of your ElastiCache for Memcached clusters, providing greater flexibility and scalability. With vertical scaling on ElastiCache for Memcached, you can now seamlessly scale up or down your Memcached instances to match your application's changing workload demands without disrupting your cluster architecture. You can scale up to boost performance and increase cache capacity during high-traffic periods, or scale down to optimise costs when demand is low. This enables you to align your caching infrastructure with your evolving application needs, enhancing cost efficiency and improving resource utilisation.

**Kubernetes**

Amazon Elastic Kubernetes Service (Amazon EKS) now offers Bottlerocket FIPS (Federal Information Processing Standards) AMIs for EKS managed node groups, helping customers to meet federal compliance requirements while leveraging the security of Bottlerocket and the operational benefits of EKS managed node groups. Bottlerocket is a Linux-based operating system optimised for running containers that follows a minimal, immutable design for enhanced security and performance. The FIPS-enabled Bottlerocket AMIs for EKS include FIPS 140-3 validated cryptographic modules and are configured by default to use FIPS-enabled AWS service endpoints, making it easier for customers in regulated industries to run containerised workloads while maintaining compliance with federal standards.

**AWS ParallelCluster**

AWS ParallelCluster 3.13 is now generally available. ParallelCluster is a fully-supported and maintained open-source cluster management tool that enables R&D customers and their IT administrators to operate high-performance computing (HPC) clusters on AWS. ParallelCluster is designed to automatically and securely provision cloud resources into elastically-scaling HPC clusters capable of running scientific and engineering workloads at scale on AWS.

Key features of this release include support for Ubuntu 24.04, an updated Slurm version 24.05.07 and support for Elastic Fabric Adapter (EFA)-enabled Amazon FSx for Lustre filesystems on official ParallelCluster AMIs. You can use EFA with your FSx Lustre filesystems to achieve higher throughput and complete jobs faster, reducing overall costs. To get started with enabling EFA with FSx Lustre filesystems on your clusters, [follow the tutorial in the ParallelCluster User Guide - Creating a cluster with an EFA-enabled FSx Lustre](https://docs.aws.amazon.com/parallelcluster/latest/ug/tutorial-efa-enabled-fsx-lustre.html?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el).

**Amazon Linux**

Amazon Linux now brings a Graphical Desktop, a new kernel option with Linux kernel 6.12, an upgraded OpenSSL to version 3.2.2, and addition of new high demand packages on AL2023.

AL2023.7 offers a modern, secure, and cloud-optimised desktop environment to Amazon Linux users. The new Graphical Desktop provides a lightweight interface designed for productivity and seamless AWS integration. The Graphical Desktop comes with GNOME 47 for a sleek UI experience. It includes other essential tools like a terminal emulator for improved CLI experience, an image viewer, a text editor, a file manager for file navigation, and Mozilla Firefox for secure web browsing. Additionally, you can connect seamlessly using Amazon DCV, enabling remote desktop access from anywhere.

The updated kernel 6.12 will help you get benefits from upstream improvements in scheduling, networking, security, and system tracing. Some of the features include EEVDF scheduling, FUSE passthrough I/O support, and enhanced eBPF support. In addition, OpenSSL has been upgraded which provides a significant performance upgrade. Finally, some of the most requested packages such as gcc14, nbd-client, nbdkit, and openDKIM will be available with AL2023.7, and this comes on the heels of recently released packages such as pam_radius, lldpad, and mod_auth_mellon.

**Swift**

The AWS IoT Device SDK team is introducing the Developer Preview for IoT Device SDK for Swift that enables developers to build Internet of Things (IoT) applications to run on Linux, macOS, iOS, and tvOS platforms. This SDK provides an idiomatic interface for iOS mobile developers to build their applications in the modern Swift language and to connect to AWS IoT services through MQTT protocol.

With the AWS IoT Device SDK for Swift, the developers can now build more sophisticated IoT applications by leveraging the native Swift integration, and the MQTT version 5 advanced features to improve error handling, client load balancing and fault tolerance with Shared Subscription, and customisation through User Properties. The SDK provides secure certificate-based authentication and supporting multiple connection methods including X.509 certificates, custom authentication, and MQTT over WebSockets connections.

Check out the [GitHub repo](https://github.com/aws/aws-iot-device-sdk-swift) as well as the supporting blog post from Vera Xia and Steve Kim, [Introducing the AWS IoT Device SDK for Swift (Developer Preview)](https://aws-oss.beachgeek.co.uk/4b2).

### Videos of the week

**Hands on with Amazon EKS Hybrid Nodes | Amazon EKS Workshop**

I was reading the blog post, [Introducing the Amazon EKS Auto Mode workshop](https://aws-oss.beachgeek.co.uk/4b5) and came across this video on Containers from the Couch, where Ray Krueger walks you through Amazon EKS Hybrid Nodes workshop module. Amazon EKS Hybrid Nodes unifies management of Kubernetes across cloud, on premises, and edge environments, driving higher scalability, availability, and efficiency. Go check it out.

{{< youtube X003oeDzhNI >}}

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes:  Luciano Mammino, Mike Chambers, James Sanders, Christian Benzolet, Waqar Ahmed Khan, Ray Krueger, Alex Kestner, Ratnopam Chakrabarti, Shivam Dubey, Suket Sharma, Veeramani A, Manoj Ponnurangam, Chris Gillespie, Jagdeep Singh Soni, Ajeet Tewari, Rupinder Grewal, Anubhav Gupta, Anusha Pininti, Geetha Penmatsa, Sriharsh Adari, Suba Palanisamy, Aarthi Srinivasan Parul Saxena, Adam Keller, Hannah Aubry, Mila Zhou, Vera Xia, Steve Kim, Juli Tera, Lavanya Tangutur,  Rajdeep Banerjee, Elizabeth Fuentes, Ikenna Izugbokwe, Steven David, Alex Kestner, Todd Neal, Neelendra Bhandari, Sai Vennam, Sameeksha Garg, Gaurav Singodia, Jagdish Pawar, RK Sai (Ravikiran Koduri), Sayan Moitra, Edward Sun, Kevin Hakanson, Lorenzo Nicora, Francisco Morillo, Sotaro Hikita, Noritaka Sekiyama, Sandeep Raveesh-Babu, Vivek Singh, Kiran Singh, Sagar Patel, James Morle, and Sébastien Stormacq.

**Feedback**

Please please please take 1 minute to [complete this short survey](https://www.pulse.aws/promotion/10NT4XZQ). 

### Stay in touch with open source at AWS

Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) for more open source goodness.

One of the pieces of feedback I received was to create a repo where all the projects featured in this newsletter are listed. Where I can hear you all ask? Well as you ask so nicely, you can meander over to[ newsletter-oss-projects](https://aws-oss.beachgeek.co.uk/3l8).

Made with ♥ from DevRel