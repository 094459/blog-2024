---
title: 'AWS open source newsletter #213'
date: '2025-08-28'
tags : [ oss-newsletter, aws open source, DocumentDB, OSCF, Strands Agent, Amazon EKS, Kubernetes, ArgoCD, KEDA, Spring AI, Bref, OpenTofu, AWS CDK, Karpenter, Apache Airflow, MWAA, dbt, PostgreSQL, MySQL, MariaDB, Apache Kafka, Apache Flink, Grafana, Amazon EMR, HBase, InfluxDB, Powertools for AWS Lambda, LangGraph, Valkey, Cedar, Mountpoint for Amazon S3, OpenZFS, AWS Parallel Computing Service, AWS Neuron ]
canonicalUrl: "https://dev.to/aws/aws-open-source-newsletter-213-33g5"
---

##  Edition #213- August 2025

Welcome to issue #213 of the AWS open source newsletter, the newsletter where I try and provide you the best open source on AWS content.  As always, this edition has more great new projects to check out. In this edition, we have a nice selection of projects that help you migrate your CDK projects, a number of graphical and text interfaces for a number of backend systems and data, a look at the Valkey client for Swift, and the usual sampling of. cool demos (which of course feature generative AI, as why wouldn't you!)

 The projects will keep you busy until next month for sure, but we also have plenty of reading material in this months newsletter. In this edition we have featured projects that include DocumentDB, Strands Agent,  Kubernetes, ArgoCD, KEDA, Spring AI, Bref, OpenTofu, AWS CDK, Karpenter, Apache Airflow,  dbt, PostgreSQL, MySQL, MariaDB, Apache Kafka, Apache Flink, Grafana, Amazon EMR, HBase, InfluxDB, Powertools for AWS Lambda, LangGraph, Valkey, Cedar, Mountpoint for Amazon S3, OpenZFS, AWS Parallel Computing Service, and AWS Neuron. That should keep you all very busy!

Check out the list of contributors at the end of the newsletter, and as always, get in touch if you want me to feature your projects in this open source newsletter. 

**Make sure you check out**

If you are using the AWS Tools for Powershell, then check out [Announcing the end-of-support for AWS Tools for PowerShell v4
](https://aws-oss.beachgeek.co.uk/4hq) for important info and timelines.

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution. The projects mentioned here do not represent any formal recommendation or endorsement, I am just sharing for greater awareness as I think they look useful and interesting!*

### Tools

**TerraTitan**

[TerraTitan](https://aws-oss.beachgeek.co.uk/4hs) is an open source (GPL) LLM powered workflow that converts AWS CDK constructs to Terraform CDK (CDKTF). This tool is a major component used to generate and maintain the TerraConstructs library, providing reliable and trustworthy infrastructure components for everyone to use. There is also [a workshop](https://aws-oss.beachgeek.co.uk/4ht) that will help you get started if this looks interesting to you.

**aws-size**

[aws-size](https://aws-oss.beachgeek.co.uk/4hv) is a great tool that **AWS Community Builder Jason Kao** that checks hard to find size limits and usage for AWS which can help provide advance warning to teams about resource limits in AWS before it's too late. Usage of these limits are not covered by AWS provided tooling such as Service Quotas and Trusted Advisor. Read the introduction blog post, [Introducing aws-size: A New Open Source Tool for Difficult Service Limit Visibility in AWS](https://www.fogsecurity.io/blog/aws-size-release) to find out more.

**iceberg_navigator**

[iceberg_navigator](https://aws-oss.beachgeek.co.uk/4hu) is a command line tool from **AWS Community Builder Aki** to makes it easy to navigate and inspect Apache Iceberg snapshot histories. It uses PyIceberg with AWS Glue REST Catalog to list, show details, and visualise snapshot lineage graphs for Iceberg tables stored on S3. He has also put together a blog post, [Building a CLI Tool to Visualize AWS Iceberg Table Snapshot History](https://dev.to/aws-builders/building-a-cli-tool-to-visualize-aws-iceberg-table-snapshot-history-4cfp) that is a helpful walkthrough of the project and code. 

**valkey-swift**

[valkey-swift](https://aws-oss.beachgeek.co.uk/4hy) is a Swift client library for Valkey. README provides everything you Swifties need to know to get all that Valkey goodness in your apps.

**q-view**

[q-view](https://aws-oss.beachgeek.co.uk/4hx) is a handy tool from **AWS Community Builder Ryan Cormack** that lets you visualise and analyse Amazon Q Developer conversation history from Q CLI. Check out the README for more details, and I will leave you with an example screenshot.

![example screenshot of tool](https://raw.githubusercontent.com/ryancormack/q-view/refs/heads/main/docs/q_summary.png)

**graphc**

[graphc](https://aws-oss.beachgeek.co.uk/4hw) (stands for "graph console")  and is a really nice interactive text user interface from **Dhruv Thakur** that lets you query Neo4j/AWS Neptune databases via the command line.  Check out the repo for screenshots and short animated videos of this in action.

**csi-components**

[csi-components](https://aws-oss.beachgeek.co.uk/4i4) - This repository contains the tooling used to build minimal Amazon Linux based versions of the Kubernetes CSI Sidecars (and other related components such as the Kubernetes CSI snapshot-controller image). These images are used in the official releases of the EBS CSI Driver versions v1.45.0 and later.

### Demos, Samples, Solutions and Workshops

**QualityFlow**

[QualityFlow](https://aws-oss.beachgeek.co.uk/4i2) is a super interesting repo from Amazon Science that demonstrates the research paper, [QualityFlow: An Agentic Workflow for Program Synthesis Controlled by LLM Quality Checks](https://aws-oss.beachgeek.co.uk/4i3). Given the English description of a programming problem and a set of unit tests, the model's goal is to synthesise the correct program that solves the problem and passes the tests. QualityFlow includes large language model (LLM) agents resembling a software development team, including code generation, testing, and self-debugging. We propose the LLM Quality Checker, which explicitly ``imagines'' whether the synthesised programs' execution would conform to the unit tests. The Quality Checks dynamically control the workflow, including actions to submit the final answer, clarify the problem statement, and revert previous workflow steps. Our experiments show that the Quality Checker can precisely accept any correct program, mitigate faulty synthesised tests, and prevent potential workflow deviation. QualityFlow establishes the state-of-the-art results on four program synthesis benchmarks: MBPP, HumanEval, and stricter evaluations from MBPP-EvalPlus and HumanEval-EvalPlus.

**sample-cost-per-transaction**

[sample-cost-per-transaction](https://aws-oss.beachgeek.co.uk/4i1) - is a repo that provides a cost intelligence solution that correlates application performance traces with Infrastructure costs, providing unprecedented transaction-level visibility to drive strategic business decisions. 

![AWS services used in solution](https://raw.githubusercontent.com/aws-samples/sample-cost-per-transaction/refs/heads/main/architecture-diagram.png)

**sample-on-demand-workflow-orchestrator**

sample-on-demand-workflow-orchestrator - this repo lets you build a serverless, dynamic workflow orchestration engine that is built with Amazon DynamoDB and AWS Lambda that enables flexible, event-driven task execution with complex dependency patterns.

![solution architecture](https://raw.githubusercontent.com/aws-samples/sample-on-demand-workflow-orchestrator/refs/heads/main/media/architecture.png)

**strands-mcp-inter-agent**

[strands-mcp-inter-agent](https://aws-oss.beachgeek.co.uk/4i5) is some sample code from my colleague James Ward that shows you how MCP Agents can call other MCP Agents by exposing them as MCP Servers. his example uses a hierarchy of agents with where the outer agent calls (using MCP) an inner agent that does routing and prompt modification, which then calls another MCP server.

**sample-sonic-java-playground**

[sample-sonic-java-playground](https://aws-oss.beachgeek.co.uk/4i0) - is a full-stack playground application for experimenting with Amazon's NovaSonic API capabilities, built with React (v18.2.0) and Spring Boot (v3.2.0). The application supports invoking NovaSonic Speech to Speech model by configuring supported parameters.

**sample-ai-agent-accelerator**

[sample-ai-agent-accelerator](https://aws-oss.beachgeek.co.uk/4hz) - if you wanted to get hands on with Amazon Bedrock AgentCore, then this repo is for you. This project is a sample reference implementation that showcases how to quickly build an AI agent using the Bedrock AgentCore building blocks. The implementation is fully serverless leveraging AgentCore Runtime, AgentCore Memory, AgentCore Observability, and Amazon S3 Vectors for Agentic RAG, eliminating the need to run databases.

The agent is built using the Strands Agent Python library and hosted on the AgentCore Runtime. It uses Strand's built-in retrieve tool to perform semantic search using Bedrock Knowledge Bases, which ingests documents from an S3 bucket and stores the indexed vectors in S3 Vectors. User conversation state and history are fully managed by AgentCore Memory. Users interact with the agent via a web app that provides both a web GUI and an HTTP JSON API, hosted as a container on ECS Fargate behind an ALB. The web app is built using Python Flask and HTMX.


### AWS and Community blog posts

**This weeks essential reading**

Here are the posts that I think are essential reads, so start here. We have more than we usually do, but thought these were all essential reads this month.

* [AWS joins the DocumentDB project to build interoperable, open source document database technology](https://aws-oss.beachgeek.co.uk/4hr) - looks at the recent announcement that AWS has joined the open source DocumentDB project under the stewardship of the Linux Foundation
* [Open Protocols for Agent Interoperability Part 4: Inter-Agent Communication on A2A](https://aws-oss.beachgeek.co.uk/4hp) - the fourth instalment of a series that is diving deep into Open Protocols for Agent Interoperability, looking at Agent-to-Agent (A2A) protocol, AWS’ involvement with the Linux Foundation-based open standard, and our support of A2A in the Strands Agents SDK [hands on]
* [Strands Agents SDK: A technical deep dive into agent architectures and observability](https://aws-oss.beachgeek.co.uk/4h8) - introduces the Strands Agents SDK, an open source framework for building AI agents, and dives into its AWS integration for secure deployments with observability features, and provides practical use cases with a step-by-step example [hands on]
* [Powering AI-Driven Security with the Open Cybersecurity Schema Framework](https://aws-oss.beachgeek.co.uk/4hn) - provides an update on the Open Cybersecurity Schema Framework (OCSF), sharing a case study, whats coming, and a look at the growing eco system
* [Building Your Open Source Commercial Strategy with AWS](https://aws-oss.beachgeek.co.uk/4ho) - dives into the topic of moving from popular open source project to profitable business, drawing on some of the experiences companies like dbt, dagger, and others 

**Community**

Each month I spend time reading posts from across the AWS community on open source topics. In this section I share what personally caught my eye and interest, and I hope that many of you will also find them interesting.

This month we start off with **AWS Community Builders Benjamen Pyle** who takes a look at how to build cloud native event driven applications on Amazon EKS using [KEDA](https://keda.sh/), an open source event based auto-scaler, in his post [KEDA to build Event-Driven Applications on EKS](https://dev.to/aws-builders/keda-to-build-event-driven-applications-on-eks-4gci). Sample code is provided so you can follow along with that one. Sticking around in cloud native land we have  **AWS Community Builders Alejandro Velez** who continues his series of posts that share production ready examples and best practices of how do automate your infrastructure configuration and deployment using GitOps with ArgoCD in the post, [GitOps and IaC at Scale – ArgoCD and Open Tofu – Part 3 – Hardening and Manage users](https://dev.to/aws-builders/gitops-and-iac-at-scale-argocd-and-open-tofu-part-3-hardening-and-manage-users-5b9m).

Regular readers of this newsletter will be familiar with the work of **AWS Heroes Vadym Kazulkin**, and he is back sharing more Java goodness in the first in a series of posts that look at Spring AI, Spring's application framework for AI engineering, and how you can get this up and running with Amazon Bedrock. In the first post [Spring AI with Amazon Bedrock - Part 1 Introduction and the sample application](https://dev.to/aws-heroes/spring-ai-with-amazon-bedrock-part-1-introduction-and-the-sample-application-4hof), he explores Spring AI and its concepts by building the conference tool application using Amazon Bedrock Converse API. Make sure you check the other posts in the series ([part two](https://dev.to/aws-heroes/spring-ai-with-amazon-bedrock-part-2-exploring-model-context-protocol-stdio-transport-3o89)was published just before I put this together)

Many moons ago, I enjoyed developing PHP code and I am happy that the community continues to thrive (go 8.5 beta!). Bref is a PHP open source runtime for AWS Lambda, enabling serverless deployment of PHP applications. **AWS Community Builder Paul Santus** shows you in a very short post,  [Introducing Bref Lambda Layers Terraform module](https://dev.to/aws-builders/introducing-bref-lambda-layers-terraform-module-1n1f), how you can automate the deployment using Terraform.  Keeping with the Terraform theme, although switching to open source, we have **AWS Community Builder kvendingoldo** who shares how set up ElastiCache Serverless with the Valkey engine by using OpenTofu in the post, [How to create AWS Serverless Valkey via OpenTofu](https://dev.to/aws-builders/how-to-create-aws-serverless-valkey-via-opentofu-40n5).

**AWS Hero Kenta Goto** looks at a topic that I know has affected me many times in my AWS CDK adventures, namely when you deploy without validating incorrect values, errors may occur during stack creation or updates. In [How to Choose Validation Approaches in AWS CDK](https://dev.to/aws-heroes/how-to-choose-validation-approaches-in-aws-cdk-2ji3) he dives into this topic and provides a number of suggestions on how to reduce these issues. Very nice post, I enjoyed this one. Sticking with AWS CDK we had the post [Different ways to conditionally provision a CDK resource](https://blog.emmanuelisenah.com/different-ways-to-conditionally-provision-a-cdk-resource) from **Emmanuel Isenah** that looks at another common use case that you will come up with as you develop your CDK stacks, namely how to deal with conditions when provisioning resources (in this case, Amazon S3 buckets) - I have had the exact same issue, so I definitely learned something reading this on how to improve my next CDK app.

Thats all for this month. If you have an open source article you want to share with the community, drop me a message (LinkedIn, or via [ricsue@amazon.co.uk](mailto:ricsue@amazon.co.uk) and I will be sure to check it out.

**Cloud Native**

* [Simplify network connectivity using Tailscale with Amazon EKS Hybrid Nodes](https://aws-oss.beachgeek.co.uk/4ha) - guides you through integrating Tailscale with your Amazon EKS Hybrid Nodes environment, a feature of Amazon EKS that enables you to streamline your Kubernetes management by connecting on-premises and edge infrastructure to an EKS cluster running on AWS [hands on]

![example hybrid architecture](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2025/08/04/CONTAINERS-36-1.png)

* [Deploy LLMs on Amazon EKS using vLLM Deep Learning Containers](https://aws-oss.beachgeek.co.uk/4hf) - demonstrates how to deploy the DeepSeek-R1-Distill-Qwen-32B model using AWS DLCs for vLLMs on Amazon EKS, showcasing how these purpose-built containers simplify deployment of this powerful open source inference engine [hands on]

![layer diagram for compute](https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2025/08/04/image-2-3.png)

* [Migrate to Amazon EKS: Data plane cost modeling with Karpenter and KWOK](https://aws-oss.beachgeek.co.uk/4hj) - looks at how to mimic a Kubernetes migration to Amazon EKS using Karpenter and KWOK, and in the process, how you can use this to estimate compute costs before progressing [hands on]

* [Introducing Seekable OCI Parallel Pull mode for Amazon EKS](https://aws-oss.beachgeek.co.uk/4hm) - explains how container image pulls work and how they impact deployment and scaling operations, diving deep into how SOCI parallel pull works, and how it can help you improve image pull performance with your workloads on Amazon EKS [hands on]

**Data and Analytics**

* [Demystifying the AWS advanced JDBC wrapper plugins](https://aws-oss.beachgeek.co.uk/4hi) - dives deep into the benefits, use cases, and implementation details for two popular AWS Advanced JDBC Wrapper Driver plugins: the Aurora Initial Connection Strategy and Failover v2 plugins [hands on]

* [Build data pipelines with dbt in Amazon Redshift using Amazon MWAA and Cosmos](https://aws-oss.beachgeek.co.uk/4he) - looks at a streamlined, configuration-driven approach to orchestrate dbt Core jobs using Amazon Managed Workflows for Apache Airflow (Amazon MWAA) and Cosmos, an open source package to simplify dbt with Apache Airflow [hands on]

* [Improve PostgreSQL performance: Diagnose and mitigate lock manager contention](https://aws-oss.beachgeek.co.uk/4h7) - explores how read heavy workloads can cause LWLock contention in PostgreSQL based systems like Amazon Aurora by exceeding fast path locking limits, and demonstrates techniques to identify and optimise queries that transition to slow path locking [hands on]

* [Optimize traffic costs of Amazon MSK consumers on Amazon EKS with rack awareness](https://aws-oss.beachgeek.co.uk/4h6) - will explain more about Apache Kafka's nearest replica fetching (rack awareness), a cost optimisation technique that reduces cross AZ traffic costs for Amazon MSK consumers on Amazon EKS by using tools like Kyverno to dynamically inject Availability Zone information into Kubernetes pods and optimise consumer routing [hands on]
* [Export JMX metrics from Kafka connectors in Amazon Managed Streaming for Apache Kafka Connect with a custom plugin](https://aws-oss.beachgeek.co.uk/4hh) - is a nice walk through that shows you how to extend the Debezium MySQL connector plugin with an additional module to export the JMX metrics to CloudWatch as custom metrics [hands on]

* [Enhance Amazon EMR observability with automated incident mitigation using Amazon Bedrock and Amazon Managed Grafana](https://aws-oss.beachgeek.co.uk/4hg) - provides a solution to automated EMR cluster monitoring and incident response, by combining real-time monitoring with AI-powered remediation suggestions and automated execution [hands on]
* [Improve Amazon EMR HBase availability and tail latency using generational ZGC](https://aws-oss.beachgeek.co.uk/4hk) - examines how unpredictable garbage collection pauses impact business critical workloads and explores the benefits of enabling generational ZGC in HBase, along with additional GC tuning techniques and new configuration parameters in Amazon EMR 7.10.0 to optimise HBase RegionServer performance and reduce tail latency [hands on]

![example graph showing generation zgc](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2025/08/05/bdb-5393-zgc_runtime_distribution-scaled.jpg)

* [Amazon Timestream for InfluxDB: Expanding managed open source time series databases for data-driven insights and real-time decision making](https://aws-oss.beachgeek.co.uk/4hl) - dives into the strengthening of the partnership between AWS and InfluxData as Amazon Timestream adopts InfluxDB as the main purpose-built time series database 

**Other posts to check out**

* [Introducing v2 of Powertools for AWS Lambda (Java)](https://aws-oss.beachgeek.co.uk/4h9) - walks you through v2 of Powertools for AWS Lambda for Java, that will help you  build robust, observable, and high-performing Serverless applications (looking at the enhanced core observability utilities, the performance gains through GraalVM native image support, and the new Kafka utility that supports using familiar Kafka patterns when working on Lambda) [hands on]

* [Using Red Hat Lightspeed AI assistant and generative AI to achieve your goals from within Red Hat Enterprise Linux (RHEL) on AWS](https://aws-oss.beachgeek.co.uk/4hc) - is a hands on walkthrough of a new AI assistant developed by Red Hat that you can use on your AWS instances of RHEL to simplify administration and more [hands on]

* [Build an intelligent financial analysis agent with LangGraph and Strands Agents](https://aws-oss.beachgeek.co.uk/4hd) - describes an approach of combining three powerful technologies to illustrate an architecture that you can adapt and build upon for your specific financial analysis needs: LangGraph for workflow orchestration, Strands Agents for structured reasoning, and Model Context Protocol (MCP) for tool integration [hands on]

![example app sequence diagram](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2025/08/07/ML-18662-4-1024x774.png)

**Case Studies**

* [How Wiz achieved near-zero downtime for Amazon Aurora PostgreSQL major version upgrades at scale using Aurora Blue/Green Deployments](https://aws-oss.beachgeek.co.uk/4h5) - provides a study into how Wiz were able to upgrade their Aurora PostgreSQL database from version 14 to 16 with near-zero downtime using Amazon Aurora Blue/Green Deployments [hands on]

* [Scaling transaction peaks: Juspay’s approach using Amazon ElastiCache](https://aws-oss.beachgeek.co.uk/4hb) - walks you through how Juspay transformed their payment processing architecture to handle transaction peaks, using Amazon ElastiCache and Amazon RDS for MySQL, to processes 7.6 million transactions per hour during peak events, whilst achieving sub-millisecond latency

### Quick updates

**Cedar**

Amazon Verified Permissions now supports Cedar 4.5. This enables customers to use the latest Cedar features, including the “is” operator, which allows customers to grant access based on resource types. For example, in a petstore application, you can use the “is” operator to write a policy that only grants administrators permission to view a resource if that resource "is" an invoice. This addition enhances Cedar's type system and helps catch potential type-related errors early in policy development. You can learn about other enhancements to [Cedar on the Cedar releases page](https://github.com/cedar-policy/cedar/releases).

**Apache Airflow**

You can now downgrade to minor Apache Airflow versions on Amazon Managed Workflows for Apache Airflow (MWAA).  Amazon MWAA is a managed orchestration service for Apache Airflow that makes it easier to set up and operate end-to-end data pipelines in the cloud. This in-place minor Apache Airflow version option allows you to downgrade your MWAA Apache Airflow version to any other [supported minor version](https://docs.aws.amazon.com/mwaa/latest/userguide/airflow-versions.html?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el#airflow-versions-official). 

**Apache Flink**

Amazon Managed Service for Apache Flink simplifies the development and operation of real-time data stream processing applications by eliminating the complexity of managing Flink infrastructure. Apache Flink is an open source framework and engine for processing data streams. Amazon Managed Service for Apache Flink now supports Amazon Key Management Service (KMS) Customer Managed Keys (CMK). Amazon Managed Service for Apache Flink has always provided encryption by default using AWS-owned KMS keys. Now, customers have the option to use their own Customer Managed Keys providing greater control on how they can encrypt data stored in MSF.

**PostgreSQL**

A few updates for PostgreSQL fans.

First up is news that Amazon RDS for PostgreSQL now supports delayed read replicas, allowing you to specify a minimum time period that a replica database lags behind a source database. This feature creates a time buffer that helps protect against data loss from human errors such as accidental table drops or unintended data modifications. In disaster recovery scenarios, you can pause replication before problematic changes are applied, resume replication up to a specific log position, and promote the replica as your new primary database. This approach enables faster recovery compared to traditional point-in-time restore operations, which can take hours for large databases.

Following that is news that Amazon RDS for PostgreSQL 18 Beta 3 is now available in the Amazon RDS Database Preview Environment, allowing you to evaluate the pre-release of PostgreSQL 18 on Amazon RDS for PostgreSQL. You can deploy PostgreSQL 18 Beta 3 in the Amazon RDS Database Preview Environment that has the benefits of a fully managed database. PostgreSQL 18 includes "skip scan" support for multicolumn B-tree indexes and improves WHERE clause handling for OR and IN conditions. It introduces parallel GIN index builds and updates join operations. Observability improvements show buffer usage counts and index lookups during query execution, along with per-connection I/O utilisation metric.

**MySQL**

Amazon Aurora MySQL - Compatible Edition 3 (with MySQL 8.0 compatibility) now supports MySQL 8.0.42 through Aurora MySQL v3.10. In addition to several security enhancements and bug fixes, MySQL 8.0.42 contains performance improvements for parallel replication using writeset dependency tracking, as well as enhanced debugging capabilities within the InnoDB storage engine. Aurora MySQL 3.10 includes an increase in maximum storage capacity from 128 TiB to 256 TiB, allowing customers to manage larger database workloads within a single database cluster. Aurora MySQL 3.10 also introduces in-memory relay log optimisation that improves binary log replication performance by caching relay log content in memory, reducing commit latency and minimising storage I/O operations on binlog replicas. For more details, refer to the Aurora MySQL 3.10 and MySQL 8.0.42 release notes. To upgrade to Aurora MySQL 3.10, you can initiate a minor version upgrade manually by modifying your DB cluster, or you can enable the “Auto minor version upgrade” option when creating or modifying a DB cluster. 

In addition to that, Amazon Relational Database Service (Amazon RDS) for MySQL now supports MySQL minor versions 8.0.43 and 8.4.6, the latest minors released by the MySQL community. We recommend upgrading to the newer minor versions to fix known security vulnerabilities in prior versions of MySQL and to benefit from bug fixes, performance improvements, and new functionality added by the MySQL community. Learn more about the enhancements in RDS for MySQL 8.0.43 and 8.4.6 in the Amazon RDS user guide. You can leverage automatic minor version upgrades to automatically upgrade your databases to more recent minor versions during scheduled maintenance windows. You can also use Amazon RDS Managed Blue/Green deployments for safer, simpler, and faster updates to your MySQL instances.

**MariaDB**

Some nice updates for MariaDB users.

Amazon Relational Database Service (Amazon RDS) for MariaDB now supports community MariaDB minor versions 11.4.8, 10.11.14 and 10.6.23. We recommend that you upgrade to the latest minor versions to fix known security vulnerabilities in prior versions of MariaDB, and to benefit from the bug fixes, performance improvements, and new functionality added by the MariaDB community. You can leverage automatic minor version upgrades to automatically upgrade your databases to more recent minor versions during scheduled maintenance windows. You can also leverage Amazon RDS Managed Blue/Green deployments for safer, simpler, and faster updates to your MariaDB instances. 

In more news, Amazon RDS for MariaDB now supports MariaDB major version 11.8, the latest long-term maintenance release from the MariaDB community. This release supports MariaDB 11.8.3 minor version. Amazon RDS for MariaDB 11.8 now supports the MariaDB Vector feature, allowing you to store vector embeddings in your database and use retrieval-augmented generation (RAG) when building your Artificial Intelligence (AI) applications. You can use MariaDB Vector to build generative AI capabilities into your e-commerce, media, health applications, and more to find similar items within a catalog. MariaDB 11.8 also introduces the ability to limit maximum size of temporary files and tables, allowing you to better manage your databases’ storage and prevent potential issues caused by oversized temporary objects. You can initiate a major version upgrade by manually modifying your DB cluster, by restoring a snapshot or by leveraging Amazon RDS Managed Blue/Green deployments to upgrade your databases to RDS for MariaDB 11.8.

**Mountpoint for Amazon S3**

Mountpoint for Amazon S3 Container Storage Interface (CSI) driver now accelerates performance for repeatedly accessed data, adds support for Security-Enhanced Linux (SELinux) mount options, and simplifies logging and permissions management. The latest version of the Mountpoint for Amazon S3 CSI driver (v2) introduces four key capabilities. First, it adds support for caching data across multiple pods. By using the new caching capabilities in Mountpoint for Amazon S3 CSI driver v2, you can finish large-scale financial simulation jobs up to 2x faster by eliminating the overhead of multiple pods individually caching the same data. Second, you can now run your Kubernetes applications on SELinux-enabled environments like Red Hat OpenShift. Third, it lets you use Amazon EKS Pod Identity to simplify how you manage access policies across Amazon EKS clusters, including cross-account access. Fourth, it simplifies how you access logs and get insights into your mounts by using kubectl, a command line tool.

**OpenZFS**

Amazon FSx now offers customers the option to use Internet Protocol version 6 (IPv6) for access to Amazon FSx for OpenZFS file systems. More and more customers are adopting IPv6 to mitigate IPv4 address exhaustion in their private networks or to satisfy government mandates such as the US Office of Management and Budget (OMB) M-21-07 memorandum. With this launch, customers can now access their file systems using IPv4, IPv6, or dual-stack clients without the need for complex infrastructure to handle IPv6 to IPv4 address translation.

**AWS Parallel Computing Service**

AWS Parallel Computing Service (AWS PCS) now supports SPANK (Slurm Plug-in Architecture for Node and job [K]control) plugins, enabling you to extend and modify how Slurm schedules and processes your high performance computing (HPC) workloads without modifying Slurm directly. Using SPANK plugins, you can now integrate AWS PCS with container technologies, implement custom monitoring of memory and I/O patterns, and dynamically modify job launches to enhance resource management. For example, you can use Enroot and Pyxis plugins to seamlessly run containerised machine learning and HPC workloads using images from Amazon Elastic Container Registry, Docker Hub, NVIDIA NGC, or other container registries. (as a side note, if you are sniggering reading this, you are not alone).

**AWS Neuron**

AWS announced the general availability of Neuron SDK 2.25.0, delivering improvements for inference workloads and performance monitoring on AWS Inferentia and Trainium instances. This latest release adds context and data parallelism support as well as chunked attention for long sequence processing in inference, and updates the neuron-ls and neuron-monitor APIs with more information on node affinities and device utilisation, respectively. This release also introduces automatic aliasing (Beta) for fast tensor operations, and adds improvements for disaggregated serving (Beta). Finally, it provides upgraded AMIs and Deep Learning Containers for inference and training workloads on Neuron.

**Kubernetes**

A few updates for cloud native folk running Kubernetes.

Amazon Elastic Kubernetes Service (Amazon EKS) now supports Kubernetes namespace configuration for AWS and Community add-ons, providing you greater control over how add-ons are organised within your Kubernetes cluster. With namespace configuration, you can now specify a custom namespace during add-on installation, enabling better organiastion and isolation of add-on objects within your EKS cluster. This flexibility helps you align add-ons with your operational needs and existing namespace strategy. Once an add-on is installed in a specific namespace, you must remove and recreate the add-on to change its namespace. This feature is available through the AWS Management Console, Amazon EKS APIs, AWS Command Line Interface (CLI), and infrastructure as code tools like AWS CloudFormation. 

Amazon EKS has expanded support for Cilium as the Container Networking Interface (CNI) for Amazon EKS Hybrid Nodes. Cilium is a Cloud-Native Computing Foundation (CNCF) graduated project that provides core networking capabilities for Kubernetes workloads. Now, you can receive support from AWS for a broader set of Cilium features when using Cilium with Amazon EKS Hybrid Nodes including application ingress, in-cluster load balancing, Kubernetes network policies, and kube-proxy replacement mode. Kubernetes clusters require a CNI for connectivity between pods running in the cluster, but most Kubernetes applications require additional components, such as ingress controllers and load balancers, to serve and secure network traffic with other external systems or users. These additional capabilities are integrated features of Cilium, built on Cilium’s eBPF-powered networking and security. Now, Amazon EKS Hybrid Nodes users can receive support from AWS for Cilium’s Ingress and Gateway features, Border Gateway Protocol (BGP) Control Plane, Load Balancer IP Address Management (LB IPAM), kube-proxy replacement, and Kubernetes network policies. AWS supports the Amazon VPC CNI for Amazon EKS nodes in AWS Cloud, which is optimized for Amazon VPC networking with built-in features such as enhanced subnet discovery, Kubernetes network policies, and multiple network interfaces per pod.

Last up is news that Amazon EKS now supports deletion protection, helping you prevent accidental termination of your EKS clusters. When enabled, deletion protection requires explicit disablement before a cluster can be deleted, providing an additional safety control for critical environments. Deletion protection is turned off by default for all new and existing clusters. You can enable deletion protection during cluster creation or any time after. To delete a protected cluster, you must first disable deletion protection for the cluster and then proceed with the cluster deletion. This two-step verification process helps prevent unintended deletions that could result from automation errors or accidental commands, especially in environments where multiple users share cluster management responsibilities. Once enabled, any attempt to delete the cluster through the AWS Management Console, EKS APIs, AWS Command Line Interface (CLI), eksctl, or infrastructure as code tools like AWS CloudFormation will be blocked until deletion protection is disabled.

### Videos of the month

**AI Agents for Platform Engineers: EKS & OSS Upgrades via Chkk Upgrade Context MCP**

Carlos Santana and Fawad Khaliq show how to give your AI coding agents (Amazon Q, Cursor, Claude Code, …) environment-aware context for upgrades and lifecycle management of OSS projects (Istio, Kafka, Keycloak, etc). They walk you through how it works, show a demo, and share what happens behind the scenes.

{% youtube SedzPt1rGGM %}

**Deploy Secure Containers on Amazon EKS with Chainguard – AWS**

In this recording, Sai Vennam from AWS details how Amazon EKS Auto Mode and Chainguard’s secure-by-default container images work together to streamline Kubernetes operations and strengthen your software supply chain. This session explores how EKS Auto Mode reduces the complexity of cluster management by automatically provisioning and scaling compute resources, while Chainguard’s hardened images help eliminate vulnerabilities by default — without sacrificing developer velocity. Sai shares actionable techniques for deploying production-ready workloads with greater efficiency and security, and wraps up with a hands-on demo to show you how easy it is to get started with these tools in tandem.

{% youtube BknFieQXSqA %}


### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes:  Sagi Tsofan, Adi Avni, Pini Dibask, Austin Groeneveld, Farooq Ashraf, Sumit Kumar, Devinder Singh, Ramesh Kumar Venkatraman, Jin Tan Ruan, Philipp Page, Lee Briggs, Curtis Rissi, Jason Janiak, Jobin Sukumaran, Boaz John, Shirish Kulkarni, Sukumar Sengottaiyan,  Vivek Gobhil, Ryan Niksch, Mayur Shetty, Evan Grenda, Karan Singh, Kihyeon Myung, Sayan Chakraborty, Cindy Li, Akhil B, Harshana Nanayakkara, Joao Palma, Vishal Naik, Sumeet Tripathi, Yu-Ting Su, Jaydev Nath, David John Chakram, Sharmila Shanmugam, Will Leach, Nirupam Datta, Ryan Moore, Riccardo Freschi, Vishal Chaudhary, Ramesh Kandasamy, Brad Bebee, Forest Vey, Victor Servin, Jesse Butler, Erez Zarum, Henry Wang, Rod Wallace,  Serge Shevchenko, Nick Aldridge, James Ward, Rashim Gupta, Emmanuel Isenah, Kenta Goto, kvendingoldo, Paul Santus, Vadym Kazulkin, Benjamen Pyle, Alejandro Velez, James Ward, Dhruv Thakur, Ryan Cormack and Jason Kao


### Stay in touch with open source at AWS

Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) for more open source goodness.

One of the pieces of feedback I received was to create a repo where all the projects featured in this newsletter are listed. Where I can hear you all ask? Well as you ask so nicely, you can meander over to[ newsletter-oss-projects](https://aws-oss.beachgeek.co.uk/3l8).

Made with ♥ from DevRel