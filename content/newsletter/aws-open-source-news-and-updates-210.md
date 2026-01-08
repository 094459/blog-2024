---
title: 'AWS open source newsletter #210'
date: '2025-05-30'
tags : [ oss-newsletter, aws open source, AWS Lambda Powertools, MCP, arctic, Strands, AWS CDK, Apache Airflow, MWAA, Valkey, KRO, Kubernetes, Amazon EKS, Finch, Spring, Localstack, Karpenter, Apache Spark, openCypher, PostgreSQL, MariaDB, MySQL, Apache Iceberg, PyIceberg, LangChain, RabbitMQ, AWS Amplify, AWS Distro for OpenTelemetry, Amazon Linux, Prometheus, Apache Kafka, OpenSearch, Slurm, AWS Parallel Computing, CrewAI, Lustre, AWS Neuron, AWS Amplify ]
canonicalUrl: "https://dev.to/aws/aws-open-source-newsletter-210-23l0"
---

##  Edition #210 - May 2025

Welcome to issue #210 of the AWS open source newsletter, the newsletter where I try and provide you the best open source on AWS content.  As always, this edition has more great new projects to check out, which include: a couple of projects for those of you looking for tools that can help you with cost optimisation, a new security threat modelling tool that uses the power of generative AI, an experimental Python SDK that offers async support, a nice UI testing tool (that will warm your spirits), and of course the now obligatory collection of MCP projects - that said, don't miss those as I think you are going to love these, including some that have been contributed by a member of the AWS Community.

The projects will keep you busy until next month for sure, but we also have plenty of reading material in this months newsletter. In this edition we have featured projects that include AWS Lambda Powertools, arctic, Strands, CrewAI, AWS CDK, Apache Airflow, Valkey, KRO, Kubernetes,  Finch, Spring, Localstack, Karpenter, Apache Spark, openCypher, PostgreSQL, MariaDB, MySQL, Apache Iceberg, PyIceberg, LangChain, RabbitMQ, AWS Amplify, AWS Distro for OpenTelemetry, Amazon Linux, Prometheus, Apache Kafka, OpenSearch, AWS Neuron, AWS Amplify, Lustre, Slurm, and AWS Parallel Computing.

As always, get in touch if you want me to feature your projects in this open source newsletter. Until the next time, I will leave you to dive into the good stuff!

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution. The projects mentioned here do not represent any formal recommendation or endorsement, I am just sharing for greater awareness as I think they look useful and interesting!*

### Tools

**aws-sdk-python**

[aws-sdk-python](https://github.com/awslabs/aws-sdk-python) is a repo that contains **experimental async clients for the AWS SDK for Python**. These new clients will allow you to interact with select AWS services that can best utilise Python's async functionality. Unlike Boto3, these clients are distributed per-service, leaving you the option to pick what fits your needs.

Please note that this new project is in early development and will be seeing rapid iteration over the coming months. This may mean instability in both public interfaces and general behaviours. Until the project releases version 1.0.0, breaking changes may occur between minor versions of the SDK. We'd strongly advise strict pinning to a version of the SDK for any non-experimental use cases.

**ecs-mcp-server**

[ecs-mcp-server](https://awslabs.github.io/mcp/servers/ecs-mcp-server/) containerises and deploys applications to Amazon ECS within minutes by configuring all relevant AWS resources, including load balancers, networking, auto-scaling, monitoring, Amazon ECS task definitions, and services. Using natural language instructions, you can manage cluster operations, implement auto-scaling strategies, and use real-time troubleshooting capabilities to identify and resolve deployment issues quickly. Check out the supporting blog post, [Enhance AI-assisted development with Amazon ECS, Amazon EKS and AWS Serverless MCP server](https://aws.amazon.com/blogs/aws/enhance-ai-assisted-development-with-amazon-ecs-amazon-eks-and-aws-serverless-mcp-server/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el).

**eks-mcp-server**

[eks-mcp-server](https://awslabs.github.io/mcp/servers/eks-mcp-server/) provides similar capabilities to the **ecs-mcp-server** project, providing AI assistants with up-to-date, contextual information about your specific EKS environment. It offers access to the latest EKS features, knowledge base, and cluster state information. This gives AI code assistants more accurate, tailored guidance throughout the application lifecycle, from initial setup to production deployment. You can dive deeper into this by reading [Accelerating application development with the Amazon EKS MCP server](https://aws.amazon.com/blogs/containers/accelerating-application-development-with-the-amazon-eks-model-context-protocol-server/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el)

**aws-serverless-mcp-server**

[aws-serverless-mcp-server](https://awslabs.github.io/mcp/servers/aws-serverless-mcp-server/) enhances the serverless development experience by providing AI coding assistants with comprehensive knowledge of serverless patterns, best practices, and AWS services. Using AWS Serverless Application Model Command Line Interface (AWS SAM CLI) integration, you can handle events and deploy infrastructure while implementing proven architectural patterns. This integration streamlines function lifecycles, service integrations, and operational requirements throughout your application development process. The server also provides contextual guidance for infrastructure as code decisions, AWS Lambda specific best practices, and event schemas for AWS Lambda event source mappings. If you want to know more, I suggest checking out [Introducing AWS Serverless MCP Server: AI-powered development for modern applications](https://aws.amazon.com/blogs/compute/introducing-aws-serverless-mcp-server-ai-powered-development-for-modern-applications/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el).

**powertools-mcp**

[powertools-mcp](https://github.com/serverless-dna/powertools-mcp) is a very nice project from **AWS Hero  Michael Walmsley** that provides search functionality for AWS Lambda Powertools documentation across multiple runtimes. This project implements an MCP server that enables Large Language Models (LLMs) to search through AWS Lambda Powertools documentation. It uses lunr.js for efficient local search capabilities and provides results that can be summarised and presented to users.  Good documentation, with examples on how to get started with MCP clients like Claude Desktop (but should work with Amazon Q CLI too)

**mkdocs-mcp**

[mkdocs-mcp](https://github.com/serverless-dna/mkdocs-mcp) is another project from **AWS Hero Michael Walmsley** that provides search functionality for any MkDocs powered site. This server relies on the existing MkDocs search implementation using the Lunr.Js search engine. In his [own words](https://www.linkedin.com/posts/walmsles_i-am-super-excited-by-the-recent-release-activity-7329456746404438017-EaCp/):

> "I am super excited by the recent release of Amazon Web Services (AWS) Strands Agent Framework. What is great is that they use MkDocs Material for their documentation. The new Serverless DNA mkdocs-mcp server lets you plug the Strands documentation into your AI Agents, including Amazon Q Cl"

The super cool thing is that this MCP server allows you to connect to any MkDocs Material published site and make the search and pages available to your AI Agents. This should help resolve those problems of how to use AI Coding Assistants with the latest projects.
	
**aws-finops-dashboard**

[aws-finops-dashboard](https://github.com/ravikiranvm/aws-finops-dashboard) is a terminal-based AWS cost and resource dashboard from **Ravi Kiran Vallamkonda** built with Python and the Rich library. It provides multi-account cost summaries by time period, service, and cost allocation tags; budget limits vs. actuals; EC2 instance status; six‑month cost trend charts; and “FinOps audit” reports (e.g. untagged or idle resources). It can export data to CSV/JSON/PDF. The gorgeous README is full of attention to detail that only an open source Builder knows, so if this sounds like a project you would find useful, give this some love.

![example txt based dashboard](https://raw.githubusercontent.com/ravikiranvm/aws-finops-dashboard/refs/heads/main/aws-finops-dashboard_trend.png)

**openops**

[openops](https://github.com/openops-cloud/openops)  is a No-Code FinOps automation platform that helps organisations reduce cloud costs and streamline financial operations. It provides customisable workflows to automate key FinOps processes like allocation, unit economics, anomaly management, workload optimisation, safe de-provisioning and much, much more. It is not limited to AWS, and you can use it across your broader technical stack. Looks interesting, so check this out.

![example workflow from openops](https://raw.githubusercontent.com/openops-cloud/openops/refs/heads/main/static/rds-workflow.png)

**sample-service-quotas-replicator-for-aws**

[sample-service-quotas-replicator-for-aws](https://github.com/aws-samples/sample-service-quotas-replicator-for-aws) is a code repo that contains sample code for the AWS Quota Replicator (AQR) tool, which demonstrates how to build a solution for comparing and managing service quotas across AWS accounts and regions. This tool was proudly built with the assistance of AWS Q Developer by **Kirankumar Chandrashekar** and **Gopinath Jagadesan**.   This tool hopes to simplify one of the most challenging aspects of AWS multi-account management: service quotas. The AWS Service Quotas Replicator helps you: 1/ Compare quotas across accounts/regions with visual indicators, 2/ Request quota increases with just a few clicks, 3/ Track request status in real-time, and 4/ Identify critical quota gaps before they impact your workloads.

This tool is perfect for account migrations, environment parity checks, multi-region deployments, and disaster recovery planning.
Check out the blog post that goes with this repo, [AWS Service Quotas Replicator: Simplifying Multi-Account/Region Quota Management](https://community.aws/content/2xW1YHGUDzbVxqCtkS6CWDmBrfD/aws-service-quotas-replicator-simplifying-multi-account-region-quota-management?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el)

**arctic**

[arctic](https://github.com/corretto/arctic) is an open-source multi platform tool developed by the Corretto Team to automate interactive UI tests. Arctic supports existing tests and is agnostic to how those tests are written. Arctic can be used to validate any type of UI test, as it does not require any special support from the application side. Arctic relies on the operating system to capture all the required events during recording time and then reproduce them during replay time. This allows Arctic to operate with older tests that were not written with automation in mind without the need to modify them.

Arctic runs on Linux, macOS (aarch64 and x86_64), and Windows (x86_64). The repo is nice and detailed, with sample screen shots and a video. 

You can explore this project in more detail by checking out the supporting blog post, [Arctic: Automated Desktop Application Testing](https://aws.amazon.com/blogs/developer/arctic-automated-desktop-application-testing/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) from **Elif Aslan** and **David Alvarez**, or if moving pictures are more your cup of tea, check out the video from **Elif Aslan**, where he provides a practical, step-by-step demonstration of Arctic. The demon showcases how Arctic can be used to record, play back, and verify UI tests through an interactive JTreg test example. 

{{< youtube diA0IPl-bEU >}}

**threat-designer**

[threat-designer](https://github.com/awslabs/threat-designer)  is a GenerativeAI application designed to automate and streamline the threat modelling process for secure system design. Harnessing the power of large language models (LLMs), it analyzes system architectures, identifies potential security threats, and generates detailed threat models. By automating this complex and time-intensive task, Threat Designer empowers developers and security professionals to seamlessly incorporate security considerations from the earliest stages of development, enhancing both efficiency and system resilience. Check out the README as it has more detail, including sample screen shots of what you can expect.

**security-hardened-amis-for-eks**

[security-hardened-amis-for-eks](https://github.com/awslabs/security-hardened-amis-for-eks) provides a fully automated solution to create security-hardened Amazon EKS AMIs that comply with either CIS Level 1 or Level 2 standards. This solution will help you if you are looking for guidance on how to generate a CIS-hardened AMI for EKS, as well as if you are encountering issues with workloads running on your own custom, CIS-hardened AMIs. Check out the README for a lot more details that are worth reviewing.

![Overview of solution](https://github.com/awslabs/security-hardened-amis-for-eks/blob/main/docs/images/solution.png?raw=true)

**eks-auto-mode-ebs-migration-tool**

[eks-auto-mode-ebs-migration-tool](https://github.com/awslabs/eks-auto-mode-ebs-migration-tool) is a tool you can use to migrate a Persistent Volume Claim from a standard EBS CSI StorageClass (ebs.csi.aws.com) to the Amazon EKS Auto EBS CSI StorageClass (ebs.csi.eks.amazonaws.com) or vice-versa. Check out the README for some important details about using this tool.

### Demos, Samples, Solutions and Workshops

**deploy-crewai-agents-terraform**

[deploy-crewai-agents-terraform](https://github.com/aws-samples/deploy-crewai-agents-terraform) is a project designed to help you perform security audits and generate reports for your AWS infrastructure using a multi-agent AI system, leveraging the powerful and flexible framework provided by CrewAI. The AWS Security Auditor Crew architecture combines CrewAI's multi-agent framework with AWS services to provide comprehensive security auditing capabilities. The system can be deployed locally or to AWS using Terraform, with Amazon Bedrock powering the AI agents.

![solution overview](https://raw.githubusercontent.com/aws-samples/deploy-crewai-agents-terraform/refs/heads/main/assets/crew-amazonbedrock.png)

### AWS and Community blog posts

**This weeks essential reading**

Here are the posts that I think are essential reads, so start here.

* [Introducing Strands Agents, an Open Source AI Agents SDK](https://aws.amazon.com/blogs/opensource/introducing-strands-agents-an-open-source-ai-agents-sdk/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) introduces a new open source SDK that takes a model-driven approach to building and running AI agents in just a few lines of code [hands on]

* [Open Protocols for Agent Interoperability Part 1: Inter-Agent Communication on MCP](https://aws.amazon.com/blogs/opensource/open-protocols-for-agent-interoperability-part-1-inter-agent-communication-on-mcp/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) is the first in a series of blog posts that look at emerging open technologies, and this one specifically looking at how MCP can be used to enable agent-to-agent communication, and highlight AWS’s efforts to simplify this pattern

* [Migrating a CDK v1 Application to CDK v2 with Amazon Q Developer](https://aws.amazon.com/blogs/devops/migrating-a-cdk-v1-application-to-cdk-v2-with-amazon-q-developer/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) looks at how you can use Amazon Q Developer to help migrate your AWS CDK v1 applications to CDK v2 [hands on]

* [How LaunchDarkly migrated to Amazon MWAA to achieve efficiency and scale](https://aws.amazon.com/blogs/big-data/how-launchdarkly-migrated-to-amazon-mwaa-to-achieve-efficiency-and-scale/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) provides a great case study on LaunchDarkly migrated and scaled to 14K tasks per day using Amazon Managed Workflows for Apache Airflow (MWAA)

![overview of MWAA architecture at LaunchDarkley](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2025/05/10/BDB-4400-ld-mwaa.png)

**Community**

Each month I spend time reading posts from across the AWS community on open source topics. In this section I share what personally caught my eye and interest, and I hope that many of you will also find them interesting.

This month Strands dominated a lot of the community mindshare, with folks discussing this new open source framework on socials, as well as coming up with some great content. Starting us off then, is **AWS Community Builder Davide De Sio** with his post, [Deploy your first AI agent with Strands Agents SDK](https://dev.to/aws-builders/deploy-your-first-ai-agent-with-strands-agents-sdk-j85) that provides a nice introduction to this topic and will get you building something in no time. My colleague **Dennis Traub** put together [Building AI Agents with Strands: A Hands-On Tutorial Series](https://community.aws/content/2xOwSRPn2OwV2nj6ZYyTxn6P7gH/building-ai-agents-with-strands-an-introduction-to-the-series?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el), a three part blog post that provides a gentle introduction and then walks you through actually creating your first AI agent with just a few lines of code using the Strands Agents SDK and Amazon Bedrock. Long time readers of this newsletter will be familiar with the works of **Gary Stafford**, creator of some of the best technical content you will read. This time he turns his attention to showing you how you can create a Perplexity-like web search agent using Strands Agents and Amazon Bedrock SoTA foundation models, including Anthropic Claude Sonnet 4 and Amazon Nova Premier in the post, [Introducing AWS Strands Agents: A New Paradigm in AI Agent Development](https://www.linkedin.com/pulse/introducing-aws-strands-agents-new-paradigm-ai-agent-gary-stafford-r5zcc/?trackingId=9W6sCdzs0ahDP1PT2eYLrQ%3D%3D). Finally, check out the Strands video at the end of this newsletter for those of you who prefer your content moving!

It wasn't all Strands though, and we had a lot of other great content produced by the community. If you like reading uber geeky stuff that goes deep into internals, then [Performance Optimization Methodology for Valkey - Part 1](https://valkey.io/blog/performance-optimization-methodology-for-valkey/) from the Valkey blog by **Lipeng Zhu** and **Wangyang Guo** of Intel is just for you. It truly deep dives into how they hunted down several performance optimisations, looking into how software is executed by the hardware.  It's accessible enough to have many takeaways for not just Valkey users but other projects as well. No round up is complete these days without an obligatory post on MCP, and so we turn to **AWS Community Builder szymon-szym** who has put together [MCP Server with AWS Lambda and HTTP Api Gateway](https://dev.to/aws-builders/mcp-server-with-aws-lambda-and-http-api-gateway-1j49) that provides a nice walk through (and code) to getting started building an MCP Server that is deployed via AWS Lambda and uses the streamable HTTP transport. Very cool indeed.

Switching to more cloud native topics we have **AWS Community Builder Kimi Huang** with his post, [KRO: A new generation tool to manage Kubernetes manifests and deployment](https://dev.to/aws-builders/kro-a-new-generation-tool-to-manage-kubernetes-manifests-and-deployment-55dm), that looks at [KRO (Kube Resource Orchestrator)](https://kro.run/) an open-source, Kubernetes-native project, that allows you to define custom Kubernetes APIs using simple and straightforward configuration. I have heard a lot of good things about this project, I just need to find some time to get hands on with it. Sticking with Kubernetes next up we have **Kashif Rafi** who put together [Introducing KAAR AI-Powered Kubernetes Cluster Analysis and Remediation](https://community.aws/content/2xJx5n22gbEQfKVrkxIDBX40oxE/kaar-ai-powered-kubernetes-cluster-analysis-and-remediation?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) a tool that automates Kubernetes Pod issue detection and resolution using k8sgpt and AWS Bedrock. Looks interesting. **Tom Jose** popped up on my timeline with his post, [Cost-Efficient Kubernetes Setup in AWS using EKS with Karpenter and Fargate](https://medium.com/kotaicode/configuring-karpenter-on-fargate-profile-98b4ff573062), a detailed walk through and explanation of setting up Amazon EKS with Karpenter using Fargate profiles, including why you should be thinking about it. To conclude this cloud native round up, I am sneaking one of my own posts next. I have switched to [Finch](https://runfinch.com/) since Jan 2024, and I regularly write about my experiences with it. This time I share how you can use it if you are using Dev Containers in VSCode, in my post [Using Finch with Dev Containers on VSCode](https://dev.to/aws/using-finch-with-dev-containers-on-vscode-2416).

**AWS Hero Rehan van der Merwe** wants you all to know about CDK Express Pipelines, so he put together this tutorial [CDK Express Pipeline Tutorial](https://rehanvdm.com/blog/cdk-express-pipeline-tutorial), that shows you how to set up and manage deployment pipelines with the cdk-express-pipeline library. Very nice post indeed, definitely check this one out. My colleague **James Wards** wants to share his enthusiasm for all things Spring in his post, [Spring AI 1.0 Brings AI to the Developer Masses](https://community.aws/content/2xLkItwKHrZ5EweKTz9uPpYHyPk/spring-ai-1-0-brings-ai-to-the-developer-masses?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) where he looks at the launch of Spring AI 1.0, a library that enables millions of developers to quickly and easily add AI to their Java and Kotlin systems. (also, don't miss out the excellent video from James in the video section below)

To finish this round up, **AWS Community Builder Lionel**takes a look at Localstack, a very cool open source tool that helps you develop locally by spoofing/emulating a bunch of AWS services. Find out more by reading [LocalStack: Emulate AWS Services for Local Development & Testing](https://dev.to/aws-builders/localstack-emulate-aws-services-for-local-development-testing-eoj?bb=23613)

**Cloud Native**

* [Streamline multi-environment deployments with Amazon EKS Blueprints and CDK pipelines](https://aws.amazon.com/blogs/containers/streamline-multi-environment-deployments-with-amazon-eks-blueprints-and-cdk-pipelines/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - shows how to set up automated pipelines for deploying and updating Amazon EKS infrastructure using the CDK pipelines module, which is part of Amazon EKS Blueprints for CDK [hands on]
* [How to automate incident response for Amazon EKS on Amazon EC2](https://aws.amazon.com/blogs/security/how-to-automate-incident-response-for-amazon-eks-on-amazon-ec2/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - helps you understand the differences between Amazon EKS and Amazon EC2 resources and how to handle EKS automation for incident response [hands on]

![solution overview](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2025/05/13/image4-1.png)

* [How Place Exchange transformed their programmatic platform with Graviton and Karpenter on Amazon EKS](https://aws.amazon.com/blogs/migration-and-modernization/how-place-exchange-transformed-their-programmatic-platform-with-graviton-and-karpenter-on-amazon-eks/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - is a case study showing how one customers multi-step journey to reduce infrastructure spending while maintaining a highly available and performant ad exchange
* [Introducing AI on EKS: powering scalable AI workloads with Amazon EKS](https://aws.amazon.com/blogs/containers/introducing-ai-on-eks-powering-scalable-ai-workloads-with-amazon-eks/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - announces the launch of AI on EKS: a new open source initiative from AWS designed to help customers deploy, scale, and optimise artificial intelligence/machine learning (AI/ML) workloads on Amazon EKS [hands on]
* [Optimizing data lakes with Amazon S3 Tables and Apache Spark on Amazon EKS](https://aws.amazon.com/blogs/containers/optimizing-data-lakes-with-amazon-s3-tables-and-apache-spark-on-amazon-eks/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - walks through how to integrate S3 Tables with Apache Spark on Amazon EKS, demonstrating how users can use this managed table service for scalable and high-performance data analytics on Amazon EKS [hands on]

**Data and Analytics**

* [Build end-to-end Apache Spark pipelines with Amazon MWAA, Batch Processing Gateway, and Amazon EMR on EKS clusters](https://aws.amazon.com/blogs/big-data/build-end-to-end-apache-spark-pipelines-with-amazon-mwaa-batch-processing-gateway-and-amazon-emr-on-eks-clusters/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - introduces Batch Processing Gateway (BPG) as a solution for routing Spark workloads across multiple EMR on EKS clusters with the help of Amazon Managed Workflows for Apache Airflow [hands on]

![solution architecture for mwaa bpg emr cluster solution](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2025/04/25/bdb-5005-architecture.png)

* [Explore the new openCypher custom functions and subquery support in Amazon Neptune](https://aws.amazon.com/blogs/database/explore-the-new-opencypher-custom-functions-and-subquery-support-in-amazon-neptune/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - describes some of the openCypher features that have been released as part of the 1.4.2.0 engine update to Amazon Neptune [hands on]
* [Unlock self-serve streaming SQL with Amazon Managed Service for Apache Flink](https://aws.amazon.com/blogs/big-data/unlock-self-serve-streaming-sql-with-amazon-managed-service-for-apache-flink/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - is a case study in how one customer successfully transitioned from ksqlDB to Managed Service for Apache Flink for its self-serve streaming SQL engine [hands on]


* [Connect Amazon Bedrock Agents with Amazon Aurora PostgreSQL using Amazon RDS Data API](https://aws.amazon.com/blogs/database/connect-amazon-bedrock-agents-with-amazon-aurora-postgresql-using-amazon-rds-data-api/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - looks at a solution to integrate generative AI applications with relational databases like Amazon Aurora PostgreSQL-Compatible Edition using RDS Data API (Data API) for simplified database interactions, Amazon Bedrock for AI model access, Amazon Bedrock Agents for task automation and Amazon Bedrock Knowledge Bases for context information retrieval [hands on]
* [Running I/O intensive workloads on PostgreSQL with Amazon EBS io2 Block Express](https://aws.amazon.com/blogs/storage/running-i-o-intensive-workloads-on-postgresql-with-amazon-ebs-io2-block-express/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - explores through the medium of benchmarks and graphs, everything you need to when you have workloads that demand high performance and sub-millisecond latencies, and where performance takes precedence over cost, Amazon EBS io2 Block Express is the ideal block storage solution [hands on]
* [Understanding transaction visibility in PostgreSQL clusters with read replicas](https://aws.amazon.com/blogs/database/understanding-transaction-visibility-in-postgresql-clusters-with-read-replicas/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - dives into the issue of transaction visibility in PostgreSQL clusters with read replicas, including what classes of architectures it might affect - this is a must read post for any users of PostgreSQL on AWS
* [Create a unit testing framework for PostgreSQL using the pgTAP extension](https://aws.amazon.com/blogs/database/create-a-unit-testing-framework-for-postgresql-using-the-pgtap-extension/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - explores how to leverage the pgTAP extension for unit testing on Amazon Relational Database Service (Amazon RDS) for PostgreSQL and Amazon Aurora PostgreSQL-Compatible Edition database, helping you build robust and reliable database applications [hands on]
* [Supercharging vector search performance and relevance with pgvector 0.8.0 on Amazon Aurora PostgreSQL](https://aws.amazon.com/blogs/database/supercharging-vector-search-performance-and-relevance-with-pgvector-0-8-0-on-amazon-aurora-postgresql/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - helps you understand how pgvector 0.8.0 on Aurora PostgreSQL-Compatible delivers up to 9x faster query processing and 100x more relevant search results, addressing key scaling challenges that enterprise AI applications face when implementing vector search at scale [hands on]


* [Melting the ice — How Natural Intelligence simplified a data lake migration to Apache Iceberg](https://aws.amazon.com/blogs/big-data/melting-the-ice-how-natural-intelligence-simplified-a-data-lake-migration-to-apache-iceberg/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - is a case study in how one customer migration to Apache Iceberg was a pivotal step in modernising the company’s data infrastructure [hands on]
* [Accelerate lightweight analytics using PyIceberg with AWS Lambda and an AWS Glue Iceberg REST endpoint](https://aws.amazon.com/blogs/big-data/accelerate-lightweight-analytics-using-pyiceberg-with-aws-lambda-and-an-aws-glue-iceberg-rest-endpoint/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - demonstrate how PyIceberg, integrated with the AWS Glue Data Catalog and AWS Lambda, provides a lightweight approach to harness Iceberg’s powerful features through intuitive Python interfaces [hands on]

**Other posts to check out**

* [Secure distributed logging in scalable multi-account deployments using Amazon Bedrock and LangChain](https://aws.amazon.com/blogs/machine-learning/secure-distributed-logging-in-scalable-multi-account-deployments-using-amazon-bedrock-and-langchain/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - presents a solution for securing distributed logging multi-account deployments using Amazon Bedrock and LangChain, addressing the critical challenge of maintaining data privacy in multi-account deployments while still enabling comprehensive observability [hands on]
* [Implementing Federation on Amazon MQ for RabbitMQ Private Brokers](https://aws.amazon.com/blogs/compute/implementing-federation-on-amazon-mq-for-rabbitmq-private-brokers/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - explains how to implement federation for Amazon MQ RabbitMQ private brokers, in a very detailed walk through [hands on]

![solution architecture](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2025/05/20/image-1.jpeg)

* [From Build to Embed: Creating and Embedding GenAI Apps with AWS Amplify, CDK, and Amazon Q Business](https://aws.amazon.com/blogs/mobile/from-build-to-embed-creating-and-embedding-genai-apps-with-aws-amplify-cdk-and-amazon-q-business/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - is the perfect post if you are looking to integrate generative AI-powered conversational experience into your applications using Amazon Q Business, AWS Amplify Gen 2, and the AWS Cloud Development Kit (CDK) [hands on]
* [Deploy to ARM-Based Compute with AWS Deploy Tool for .NET](https://aws.amazon.com/blogs/developer/deploy-to-arm-based-compute-with-aws-deploy-tool-for-net/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - announces the AWS Deploy Tool for .NET now supports deploying .NET applications to select ARM-based compute platforms on AWS [hands on]
* [Tracing ETL Workloads using AWS X-Ray and AWS Distro for OpenTelemetry](https://aws.amazon.com/blogs/mt/tracing-etl-workloads-using-aws-x-ray-and-aws-distro-for-opentelemetry/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) -  provides an end-to-end observability view of a data pipeline workflow by propagating context and tracing individual operations through AWS Distro for OpenTelemetry and AWS X-Ray, that enables data engineers to quickly troubleshoot failures, optimise performance, and gain insights into how data characteristics impact downstream processing [hands on]
* [Port .NET Framework workloads to Linux with Amazon Q Developer, Part 4: MVC projects](https://aws.amazon.com/blogs/dotnet/port-net-framework-workloads-to-linux-with-amazon-q-developer-part-4-mvc-applications/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - continues from previous posts, this time focusing on migrating ASP.NET MVC applications to ASP.NET Core [hands on]
* [Simplify AWS AppSync Events integration with Powertools for AWS Lambda](https://aws.amazon.com/blogs/mobile/simplify-aws-appsync-events-integration-with-powertools-for-aws-lambda/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - looks at how the AppSyncEventsResolver in Powertools for AWS enhances your development experience with AppSync Events by providing a simple and consistent interface for processing real-time event [hands on]
* [Build Golden Images with CIS Linux Build Kit within Amazon EC2 Image Builder](https://aws.amazon.com/blogs/mt/build-golden-images-with-cis-linux-build-kit-within-amazon-ec2-image-builder/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - walks you through how to setup an EC2 Image Builder based process to harden an Amazon Linux 2 AMI as stated by the CIS Amazon Linux 2 Benchmark using the Linux Build Kit provided by CIS Community [hands on]
* [Enhanced remote desktop experience: Amazon DCV with Amazon Linux 2023](https://aws.amazon.com/blogs/compute/enhanced-remote-desktop-experience-amazon-dcv-with-amazon-linux-2023/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - introduces the new Graphical Desktop with Amazon Linux 2023 (AL2023) and provides an overview of new features available through DCV [hands on]
* [Amazon FSx for Lustre launches new storage class with the lowest-cost and only fully elastic Lustre ﬁle storage](https://aws.amazon.com/blogs/aws/amazon-fsx-for-lustre-adds-new-storage-class-with-the-lowest-cost-and-only-fully-elastic-lustre-file-storage/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - covers  the general availability of the Amazon FSx for Lustre Intelligent-Tiering, a new storage class that delivers virtually unlimited scalability, the only fully elastic Lustre ﬁle storage, and the lowest cost Lustre file storage in the cloud

### Quick updates

**Kubernetes**

Amazon Elastic Kubernetes Service (EKS) announces the general availability of EKS Dashboard, a new feature that provides centralised visibility into Kubernetes infrastructure across multiple AWS Regions and accounts. EKS Dashboard provides comprehensive insights into your Kubernetes clusters, enabling operational planning and governance. You can access the Dashboard in EKS console through AWS Organisations' management and delegated administrator accounts. As you expand your Kubernetes footprint to address operational and strategic objectives, such as improving availability, ensuring business continuity, isolating workloads, and scaling infrastructure, the EKS Dashboard provides centralised visibility across your Kubernetes infrastructure. You can now visualise your entire Kubernetes infrastructure without switching between AWS Regions or accounts, gaining aggregated insights into clusters, managed node groups, and EKS add-ons. This includes clusters running specific Kubernetes versions, support status, upcoming end of life auto-upgrades, managed node group AMI versions, EKS add-on versions, and more. This centralised approach supports more effective oversight, auditability, and operational planning for your Kubernetes infrastructure.

Dive deeper into this by reading **Micah Walter's** blog post, [Centralize visibility of Kubernetes clusters across AWS Regions and accounts with EKS Dashboard](https://aws.amazon.com/blogs/aws/centralize-visibility-of-kubernetes-clusters-across-aws-regions-and-accounts-with-eks-dashboard/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el)

![Overview and example dashboards](https://d2908q01vomqb2.cloudfront.net/da4b9237bacccdf19c0760cab7aec4a8359010b0/2025/05/19/eks-dashboard-01-1024x854.png)

**Prometheus**

Amazon Managed Service for Prometheus, a fully managed Prometheus-compatible monitoring service, now provides the capability to identify expensive PromQL queries, and limit their execution. This enables customers to monitor and control the types of queries being issued against their Amazon Managed Service for Prometheus workspaces. Customers have highlighted the need for tighter governance controls for queries, specifically around high cost queries. You can now monitor queries above a certain Query Samples Processed (QSP) threshold, and log those queries to Amazon CloudWatch. The information in the vended logs allows you to identify expensive queries. The vended logs contain the PromQL query and metadata about where it originated from, such as from Grafana dashboard IDs or alerting rules.
In addition, you can now set warning or error thresholds for query execution. To control query cost, you can pre-empt the execution of expensive queries by providing an error threshold in the HTTP headers to the QueryMetrics API. Alternatively, by setting a warning threshold, we return the query results, charge you for the QSP, and return a warning to the end-user that the query is more expensive than the limit set by your workspace administrator.

Just in before I published this newsletter was news that Amazon Managed Service for Prometheus now supports queries with time ranges up to 95 days, an increase from the previous 32-day limit. With this feature, customers can query any 95-day window, including historical data, allowing them to perform month-over-month comparisons, analyse long-term system trends and review historical incidents. This feature is now available across all Amazon Managed Service for Prometheus workspaces in all regions where the service is available.

**MariaDB**

Amazon Relational Database Service (Amazon RDS) for MariaDB now supports community MariaDB minor versions 10.5.29 and 10.6.22. We recommend that you upgrade to the latest minor versions to fix known security vulnerabilities in prior versions of MariaDB, and to benefit from the bug fixes, performance improvements, and new functionality added by the MariaDB community.

**PostgreSQL**

In May we saw a few version updates for PostgreSQL.

* Amazon Aurora now supports PostgreSQL major version 17 (17.4). This release contains product improvements and bug fixes from the PostgreSQL community along with Aurora- specific feature improvements such as enhanced memory management, faster storage metadata initialization during failovers, and optimized write-heavy workloads on new Graviton 4 high-end instances. This release also includes new features for Babelfish, Aurora-specific security fixes, and updates to key extensions including pgvector 0.8.0 and postgis 3.5.1. 

* Amazon RDS for PostgreSQL now supports the latest minor versions 17.5, 16.9, 15.13, 14.18, and 13.21. We recommend that you upgrade to the latest minor versions to fix known security vulnerabilities in prior versions of PostgreSQL, and to benefit from the bug fixes added by the PostgreSQL community. This release also includes updates for PostgreSQL extensions such as pg_repack 1.5.1, pg_logical 2.4.5 and others.

* Amazon Aurora PostgreSQL Limitless Database is now available with PostgreSQL version 16.8 compatibility, bringing significant improvements and new features. This release contains product improvements and bug fixes made by the PostgreSQL community, along with Aurora Limitless-specific additions such as support for the ltree extension, the btree_gist extension, and improved query performance.

Amazon RDS for PostgreSQL 18 Beta 1 is now available in the Amazon RDS Database Preview Environment, allowing you to evaluate the pre-release of PostgreSQL 18 on Amazon RDS for PostgreSQL. You can deploy PostgreSQL 18 Beta 1 in the Amazon RDS Database Preview Environment that has the benefits of a fully managed database. PostgreSQL 18 includes significant updates to query execution and I/O operations. Query execution is enhanced with "skip scan" support for multicolumn B-tree indexes and optimised WHERE clause handling for OR and IN (...) conditions. Parallel execution capabilities are expanded through parallel GIN index builds and enhanced join operations. Observability improvements include detailed buffer access statistics in EXPLAIN ANALYZE and enhanced I/O utilisation monitoring capabilities. Please refer to the PostgreSQL community announcement for more details. Amazon RDS Database Preview Environment database instances are retained for a maximum period of 60 days and are automatically deleted after the retention period. Amazon RDS database snapshots that are created in the preview environment can only be used to create or restore database instances within the preview environment. You can use the PostgreSQL dump and load functionality to import or export your databases from the preview environment.

**MySQL**

Amazon Aurora MySQL - Compatible Edition 3 (with MySQL 8.0 compatibility) now supports MySQL 8.0.40 through Aurora MySQL v3.09. In addition to several security enhancements and bug fixes, MySQL 8.0.40 contains enhancements that improve database availability when handling large number of tables and reduce InnoDB issues related to redo logging, and index handling. Aurora MySQL 3.09 includes performance enhancements to improve write throughput for 32xl and larger instances running on I/O-Optimised configuration. This release also contains improvements that increase the cross-region resiliency of Aurora Global Database secondary region clusters. For more details, refer to the Aurora MySQL 3.09 and MySQL 8.0.40 release notes. To upgrade to Aurora MySQL 3.09, you can initiate a minor version upgrade manually by modifying your DB cluster, or you can enable the “Auto minor version upgrade” option when creating or modifying a DB cluster.

In more Amazon RDS for MySQL news, it now supports MySQL minor versions 8.0.42 and 8.4.5, the latest minors released by the MySQL community. We recommend upgrading to the newer minor versions to fix known security vulnerabilities in prior versions of MySQL and to benefit from bug fixes, performance improvements, and new functionality added by the MySQL community.

In the last bit of MySQL news for this edition, Amazon RDS for MySQL now supports new Amazon RDS Extended Support minor version 5.7.44-RDS.20250508. We recommend that you upgrade to this version to fix known security vulnerabilities and bugs in prior versions of MySQL. Learn more about upgrading your database instances, including minor and major version upgrades, in the Amazon RDS User Guide. Amazon RDS Extended Support provides you more time, up to three years, to upgrade to a new major version to help you meet your business requirements. During Extended Support, Amazon RDS will provide critical security and bug fixes for your MySQL databases on Aurora and RDS after the community ends support for a major version. You can run your MySQL databases on Amazon RDS with Extended Support for up to three years beyond a major version’s end of standard support date. 

**Apache Kafka**

Amazon Managed Streaming for Apache Kafka (Amazon MSK) now supports Apache Kafka version 4.0, bringing the latest advancements in cluster management and performance to MSK Provisioned. Kafka 4.0 introduces a new consumer rebalance protocol, now generally available, that helps ensure smoother and faster group rebalances. In addition, Kafka 4.0 requires brokers and tools to use Java 17, providing improved security and performance, includes various bug fixes and improvements, and deprecates metadata management via Apache ZooKeeper. To start using Apache Kafka 4.0 on Amazon MSK, simply select version 4.0.x when creating a new cluster via the AWS Management Console, AWS CLI, or AWS SDKs. You can also upgrade existing MSK provisioned clusters with an in-place rolling update. Amazon MSK orchestrates broker restarts to maintain availability and protect your data during the upgrade.

**OpenSearch**

You can now run OpenSearch version 2.19 in Amazon OpenSearch Service which introduces several improvements in the areas of Vector Search, Observability and OpenSearch Dashboards.

We have introduced four key capabilities for vector search applications. The Faiss engine now supports AVX512 SIMD instructions, to accelerate vector similarity computations. The ML inference search response processor can now rank search hits and update scores based on model predictions, enabling sophisticated and context-aware document ranking and result augmentation. Lucene binary vectors, now complement existing Faiss engine binary vector support offering greater flexibility for vector search applications. Hybrid search now includes pagination support , reciprocal rank fusion to improve result ranking along with a debugging tool for score and rank normalisation process.

The launch also introduces query insights dashboards that lets users monitor and analyse the top queries collected by the query Insights plugin. Anomaly detection now offers two key improvements. First, enhanced anomaly definition capabilities allow users to specify multiple criteria to identify both spikes and dips in data patterns. Second, a new dedicated index for flattened results improves query performance and dashboard visualisation experience. Finally, you can now use template query to create search queries that contain placeholder variables allowing for more flexible, efficient, and secure search operations.

**AWS Parallel Computing Service (PCS)**

AWS Parallel Computing Service (PCS) now supports Slurm version 24.11 with support for managed accounting. Using this feature, you can enable accounting on your PCS clusters to monitor cluster usage, enforce resource limits, and manage fine-grained access control to specific queues or compute node groups. PCS manages the accounting database for your cluster, eliminating the need for you to setup and manage a separate accounting database.

**AWS Amplify**

AWS Amplify Hosting is excited to offer customisable build instances to provide you with more memory and CPU configurations to build your applications. This new feature allows developers to select from multiple build instances to optimise their build environment based on their application's specific requirements. Developers can now choose from three instance types: (Default) Standard (8 GB Memory, 4 vCPUs), Large (16 GB Memory, 8 vCPU), and XLarge (72 GB Memory, 36 vCPU).  You can adjust the build instance on any Amplify app in the in the Amplify Console under Hosting→ Build settings.

Check out the post from Matt Auerbach for more details on how to get started, [Introducing Upgraded Build Instances on Amplify Hosting](https://aws.amazon.com/blogs/mobile/introducing-upgraded-build-instances-on-amplify-hosting/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el)

**AWS Neuron**

AWS announced the release of Neuron 2.23, featuring enhancements across inference, training capabilities, and developer tools. This release moves the NxD Inference library (NxDI) to general availability (GA), introduces new training capabilities including Context Parallelism and ORPO, and adds support for PyTorch 2.6 and JAX 0.5.3. The NxD Inference library moves from beta to general availability, now recommended for all multi-chip inference use-cases. Key enhancements include Persistent Cache support to reduce compilation times and optimised model loading time.

For training workloads, the NxD Training library introduces Context Parallelism support (beta) for Llama models, enabling sequence lengths up to 32K. The release adds support for model alignment using ORPO with DPO-style datasets, upgraded support for 3rd party libraries, specifically: PyTorch Lightning 2.5, Transformers 4.48, and NeMo 2.1.

The Neuron Kernel Interface (NKI) introduces new 32-bit integer operations, improved ISA features for Trainium2, and new performance tuning APIs. The Neuron Profiler now offers 5x faster profile result viewing, timeline-based error tracking, and improved multiprocess visualization with Perfetto.

### Videos of the month

**Model Driven Agents - Strands Agents (A New Open Source, Model First, Framework for Agents)**

My colleagues **Mike Chambers, Ryan Coleman, Clare Liguori**, and **Suman Debnath** introduce Strands Agents, an new open source framework that leverages the full power of modern Language Models. Built and production-tested by AWS teams, Strands Agents represents a fundamental shift in how we build AI agents.

{{< youtube Ausm87d5Ry8 >}}

**Open Source Observability on AWS**

In today's cloud-native landscape, organisations face the growing challenge of implementing comprehensive observability while managing the complexity of distributed systems. This Containers from the Couch session introduces a powerful approach to observability through the integration of Amazon Managed Service for Prometheus, Amazon Managed Grafana, and Amazon OpenSearch, demonstrating how to build a complete observability stack without the operational overhead. It provides a deep dive into these managed services' capabilities, showcasing how they work together to provide a unified platform for metrics, logs, and traces, enabling organisations to implement enterprise-grade observability solutions at scale.

{{< youtube pxpVhJ2P164 >}}

**Write Once, Deploy Everywhere: From Containers to Serverless**

This recorded talk from **James Ward** and **Matthew Meckes** walks you through different approaches you can take to make deploying your Spring applications work across different deployment options. It looks at how to abstract service configuration / bindings,  utilise Testcontainers across local dev/test & CI,  efficiently avoid cold starts with CRaC and other techniques, and how to package applications most efficiently for the target platform

{{< youtube 8kgNmuvq6gQ >}}

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes: Sofie Zilberman, Gal Krispel, Lorenzo Nicora, Shayon Sanyal, Aritra Gupta, Ratnopam Chakrabarti, Manabu McCloskey, Vara Bonthu, Omri Shiv, Veliswa Boya, Matt Auerbach, Niall Thomson, Carlos Santana, George John, Elizabeth Fuentes, Shridhar Pandey, Ben Freiberg, Michael Walmsley, Ravi Kiran Vallamkonda, Kirankumar Chandrashekar, Gopinath Jagadesan, James Wards, Lionel, Rehan van der Merwe, Kashif Rafi, Kimi Huang, Lipeng Zhu, Wangyang Guo, Davide De Sio, Dennis Traub, Gary Stafford, Mike Chambers, Ryan Coleman, Clare Liguori, Suman Debnath, Matthew Meckes, Micah Walter, Elif Aslan, David Alvarez, Nick Aldridge, Marc Brooker, Swami Sivasubramanian, Dr. Rahul Sharad Gaikwad, Tamilselvan P, Vinodkumar Mandalapu, Asena Uyar, Dean Verhey, Daniel Lopes, Tom Jose, Avinash Desireddy, Suvojit Dasgupta, Kevin Phillips, Nihilson Gnanadason, Senthil Moha, Elamaran Shanmugam, Mikhail Shapirov, Jayaprakash Alawala, Bhavye Sharma, Jonathan Nguyen, Gopinath Jagadesan, Kenny Guzman, Karl Sung, Ishita Chakraborty, Vinodh Kannan Sadayamuthu, Mohammad Tahsin, Felipe Lopez, Aswin Vasudevan, Saumya Mula, Rachanee Singprasong, Ben-Amin York Jr., Dexter Pham, Dianne Eldridge, Vaidehi Patel, Philippe El Asmar, Sergey Melnik, Praneeth Reddy Tekula, Deepak Kovvuri, Viveyk Karri, Yonatan Dolan, Haya Axelrod Stern, Zion Rubin, Michal Urbanowicz, Neha Sharma, Vishal Sanzira, Venkata Prasad Reddy Somala, Sotaro Hikita, Shuhei Fukami, Ty Augustine, Sylvester Creado, Pavankumar Kasani, Ana Falcao, Leandro Cavalcante Damascena, Rajat Chatterjee, Madhur Kulkarni and Andrew Morgan

**Feedback**

Please please please take 1 minute to [complete this short survey](https://www.pulse.aws/promotion/10NT4XZQ). 

### Stay in touch with open source at AWS

Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) for more open source goodness.

One of the pieces of feedback I received was to create a repo where all the projects featured in this newsletter are listed. Where I can hear you all ask? Well as you ask so nicely, you can meander over to[ newsletter-oss-projects](https://github.com/094459/newsletter-oss-projects).

Made with ♥ from DevRel