---
title: 'AWS open source newsletter #215'
date: '2025-10-31'
tags : [ oss-newsletter, aws open source, Valkey, Redis, AWS CDK, CDK Booster, Fluent Bit, Strands Agents SDK, LangChain, Streamlit, Argo CD, Slurm, KubeArmor, Red Hat OpenShift, ROSA, Apache Iceberg, MySQL, MariaDB, Apache Kafka, InfluxDB, OpenSearch, LocalStack, LibreOffice, Apache Flink, Amazon Corretto, OpenJDK, Apache Airflow, Apache Arrow, Apache DataFusion, Parquet, Apache Cassandra, Amazon Keyspaces, AWS SAM, Finch, Kubernetes, Amazon EKS, Amazon EKS Distro, eksctl, OpenTelemetry, AWS ParallelCluster, Amazon Linux, Smithy ]
canonicalUrl: "https://dev.to/aws/aws-open-source-newsletter-215-46im"
---


##  Edition #215 - October 2025

Welcome to issue #215 of the AWS open source newsletter, the only newsletter that I know of that brings you the best open source on AWS content.  There is nothing spooky or scary in this months edition we have a nice selection of projects that cover a broad range of use cases - tools to help you with CloudFormation stacks, provide a GUI layer over your Amazon S3 buckets, terminal user interfaces to work with Amazon ECS and your AWS profiles, a couple of nice tools to simplify building agentic applications using Strands Agents, and more. We also have some really cool demos that include showing how you can move from monolith to modern application (including thinking about portability, building AI powered SLDC architectures, and a really neat use of the Nitro Enclaves feature of Nitro EC2 instances. Some great stuff this month.

The projects will keep you busy until next month for sure, but we also have plenty of reading material in this months newsletter. In this edition we have featured projects that include Valkey, Redis, AWS CDK, CDK Booster, Fluent Bit, Strands Agents SDK, LangChain, Streamlit, Argo CD, Slurm, KubeArmor, Red Hat OpenShift, ROSA, Apache Iceberg, MySQL, MariaDB, Apache Kafka, InfluxDB, OpenSearch, LocalStack, LibreOffice, Apache Flink, Amazon Corretto, OpenJDK, Apache Airflow, Apache Arrow, Apache DataFusion, Parquet, Apache Cassandra, Amazon Keyspaces, AWS SAM, Finch, Kubernetes, Amazon EKS, Amazon EKS Distro, eksctl, OpenTelemetry, AWS ParallelCluster, Amazon Linux, and Smithy . That should keep you all very busy!

Check out the list of contributors at the end of the newsletter, and as always, get in touch if you want me to feature your projects in this open source newsletter. 

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution. The projects mentioned here do not represent any formal recommendation or endorsement, I am just sharing for greater awareness as I think they look useful and interesting!*

### Tools

**nicebucket**

[nicebucket](https://github.com/nicebucket-org/nicebucket) if you are looking for a GUI to manage your Amazon S3 buckets, then this project is for you. Some of the features include the ability to browse any S3-compatible bucket (S3, R2, etc.) like local folders, upload files individually, download files individually, create and delete folders, move files between folders, and preview files without downloading. The tool provides secure credential management using your system's keyring. Check out the README for some video demos of this tool and what it looks like.

**delstack**

[delstack](https://github.com/go-to-k/delstack) is a pretty handy tool for those situations (and we have ALL been there) when we get stuck waiting for CloudFormation stacks to delete. This open source tool from **AWS Hero Kenta Goto** helps you to force delete the entire AWS CloudFormation stack, even if it contains resources that fail to delete by the CloudFormation delete operation. Check out the README for a demo video and lots of details on how to configure this tool.

**tokenex**

[tokenex](https://github.com/riptideslabs/tokenex) this library provides a unified interface for obtaining and refreshing credentials from various cloud providers and authentication systems. It is designed to facilitate secure access to cloud resources by exchanging identity tokens for temporary credentials. **Toader Sebastian** has put together a supporting blog post that explains why they built this, so if this library sounds interesting to, go check it out - [Introducing tokenex: an open source Go library for fetching and refreshing cloud credentials](https://riptides.io/blog-post/introducing-tokenex-an-open-source-go-library-for-fetching-and-refreshing-cloud-credentials)

**ecs-voyager**

[ecs-voyager ](https://github.com/benbpyle/ecs-voyager) **AWS Community Builder Benjamen Pyle** has created an open source terminal user interface (TUI) for exploring and managing AWS ECS resources, inspired by k9s for Kubernetes (and built in Rust). Check out the README for detailed instructions on how to use this tool, and go on a voyage of your own!

**anywhere-mesh**

[anywhere-mesh](https://github.com/kloudcover/anywhere-mesh)  is a Rust based ingress and client pair that lets ECS Anywhere tasks register themselves over WebSockets and receive HTTP traffic tunnelling from an AWS Application Load Balancer (ALB). The repository also ships sample services, k6 scenarios, and infrastructure automation used to validate the mesh. **Kevin Truckenmiller** shared the reasons for creating this tool on the aws subreddit which you can [read here](https://www.reddit.com/r/aws/comments/1ny5nlq/built_a_lightweight_rustbased_mesh_for_ecs/).

> Most service meshes (Istio, Consul, etc.) are awesome but heavy if you just need routing and connectivity between environments. I wanted something that:
> Works natively with AWS ECS Anywhere
> Doesn’t require Kubernetes or control planes
> Uses WebSockets for persistent cloud to edge routing
> Handles host-based routing, health checks, and optional IAM validation
>
> It’s just a single binary (mesh) that runs as an ingress or client. Right now I’m gathering feedback because I like it, but wonder if anyone else has a purpose for it.

Kevin is looking for feedback, so if this tool sounds useful give it a go and let Kevin know what you think.

**awsui**

[awsui](https://github.com/junminhong/awsui)  **junminhong (jasper)** has created a modern text based UI (TUI) for AWS that enables fast profile switching, seamless SSO re-auth, Amazon Q integration, smart CLI autocomplete, and bilingual UI. Jasper shared the origin story of this tool [on Reddit](https://www.reddit.com/r/aws/comments/1nvaq20/awsuia_modern_textualpowered_aws_cli_tui/), and you find out more by checking the README.

![demo of awsui](https://github.com/junminhong/awsui/blob/main/images/demo01.png?raw=true)

**sample-strands-visual-builder**

[sample-strands-visual-builder](https://github.com/aws-samples/sample-strands-visual-builder) provides a sample visual development platform for building, deploying, and managing Strands AI agents with drag-and-drop components, AI-powered code generation, and seamless AWS AgentCore integration. Strands Visual Builder is a development and learning platform that provides a complete visual development environment for experimenting with AI agents. Design complex agent workflows using an intuitive drag-and-drop canvas, leverage an expert AI agent for intelligent code generation, and deploy to AWS AgentCore for testing and evaluation. This sample application demonstrates advanced AI agent development patterns and serves as a learning tool for developers exploring the Strands SDK.

![demo architecture for strands visual builder](https://raw.githubusercontent.com/aws-samples/sample-strands-visual-builder/refs/heads/main/strands-vb-arch.png)

**strands studio ui**

[strands studio ui](https://github.com/xiehust/strands_studio_ui/)  **xiehust** has put together a cool looking project that provides a visual drag-and-drop interface for creating, configuring, and executing AI agent workflows. Build complex agent interactions through an intuitive node-based editor that generates Python code using the Strands Agent SDK.

![strands studio ui demo](https://raw.githubusercontent.com/xiehust/strands_studio_ui/refs/heads/main/assets/image-1.png)

**strands-agentcore-tools**

[strands-agentcore-tools](https://github.com/cagataycali/strands-agentcore-tools) is a project from **cagataycali** that provide a bunch of new tools for the Strands Agent framework that make it easier to work with Amazon Bedrock AgentCore. It wraps AWS Bedrock AgentCore boto3 APIs for deployment, invocation, monitoring, and lifecycle management.  Check out the README for the list of nine tools that this library will add, as well as sample code to get you started. 

**runbox-cloud**

[runbox-cloud](https://github.com/dacort/runbox-cloud) regularly featured in this newsletter, **Damon Cortesi** got in touch to share info about his latest creation. runbox-cloud allows you to spin up an entire EC2 environment (vpc/iam/etc) with a single command, and then immediately spin it down. The other fun thing is it uses another tool Damon created, [Python SSM client](https://github.com/dacort/pyssm-client).  Check out the README for some recipes on how you can test/run this.

**mcp-amqp-transport**

[mcp-amqp-transport ](https://github.com/amazon-mq/mcp-amqp-transport) this repo provides an AMQP transport implementation for the Model Context Protocol (MCP), enabling MCP servers and clients to communicate over AMQP message brokers like RabbitMQ. The package includes two CLI tools for bridging stdio-based MCP implementations with AMQP, and the README provides various examples of how you can run this.

**gpt-oss.java**

[gpt-oss.java ](https://github.com/amzn/gpt-oss.java) provides a pure Java implementation of OpenAI's gpt-oss inference in ~1000 lines of code optimised for CPU execution. Inspired by llama.cpp, llama2.c, this repo ports the gpt-oss PyTorch model.py to efficient Java code, emphasising minimalism, simplicity, and educational purpose. Check the README for machine requirements (the higher spec machine the better) as well as some benchmark results.

* Apple M3 Pro (12 cores, 36GB RAM): Decode: avg 8.7 tokens/sec, Prefill: avg 11.8 tokens/sec
* AWS EC2 m5.4xlarge (Intel Xeon Platinum 8175M, 8 physical cores, 16 vCPUs, 64GB RAM): Decode: avg 6.8 tokens/sec, Prefill: avg 10 tokens/sec

**sample-portable-app-deploy-on-aws**

[sample-portable-app-deploy-on-aws](https://github.com/aws-samples/sample-portable-app-deploy-on-aws/) is an interesting repo that provides a hands-on journey of transforming a monolith application  into a sophisticated clean architecture implementation. But that's not all – you'll also discover how to maintain deployment flexibility across various AWS compute services, a critical skill in today's cloud-native world.  This project demonstrates various deployment options on AWS compute services, including AWS Lambda, Amazon ECS, and Amazon EKS. By implementing best architecture principles, the application remains portable and deployment-agnostic, mitigating vendor or even service lock-in concerns. You'll discover how well-architected software can be efficiently deployed across different technologies and AWS services while maintaining its core functionality and structure.

![overview of project](https://raw.githubusercontent.com/aws-samples/sample-portable-app-deploy-on-aws/refs/heads/main/docs/images/ArchitecturalEvolution.png)

**sample-splunk-eks-controlplane-logs-ingestion**

[sample-splunk-eks-controlplane-logs-ingestion](https://github.com/aws-samples/sample-splunk-eks-controlplane-logs-ingestion) is some sample code that is deployed as an AWS Lambda function that processes Amazon EKS control plane logs from CloudWatch Logs and forwards them to Splunk via HTTP Event Collector (HEC). This Lambda function is designed to be triggered by CloudWatch Logs subscription filters to process EKS control plane logs and send them to Splunk. It handles log decompression, metadata enrichment, and proper formatting for Splunk ingestion. Check out the README for configuration options and installation details.

### Demos, Samples, Solutions and Workshops

**sample-ai-powered-sdlc-patterns-with-aws**

[sample-ai-powered-sdlc-patterns-with-aws](https://github.com/aws-samples/sample-ai-powered-sdlc-patterns-with-aws) is a repo repo contains AI-powered software development patterns showing how to integrate generative AI in different stages of software development lifecycle using Amazon Q Developer, Amazon Q Business and Amazon Bedrock. This collection of patterns demonstrates practical approaches for leveraging AWS's generative AI capabilities across the software development lifecycle (SDLC). The patterns are designed to help development teams enhance productivity, improve quality, and accelerate delivery through AI-powered development.

![overview of solution](https://raw.githubusercontent.com/aws-samples/sample-ai-powered-sdlc-patterns-with-aws/refs/heads/main/all-phases/sdlc-knowledge-management/generated-diagrams/ai-assistant-architecture.png)

**mcp-oauth2-aws-cognito**

[mcp-oauth2-aws-cognito](https://github.com/empires-security/mcp-oauth2-aws-cognito) this repository demonstrates how to secure a Model Context Protocol (MCP) server using OAuth 2.1 authorisation flows, implemented entirely with Node.js and Express.js. While this example uses AWS Cognito as the backing authorisation server, the implementation is provider-agnostic and can work with any OAuth 2.1 compliant authorisation server. Detailed README which will help you get it up and running - in fact, I did actually get this project running for the MCP Summit event in London, so I can confirm it worked for me. I used MCP Inspector to test it out. Let me know how you get on if you give it a go.

**sample-mpc-app-using-aws-nitrotpm**

[sample-mpc-app-using-aws-nitrotpm](https://github.com/aws-samples/sample-mpc-app-using-aws-nitrotpm) is a really neat demo that showcases one of my favourite features of Nitro based Amazon EC2 instances, Trusted Execution Environment (TPM-TEE). The repo provides code that showcases how secure collaboration between LLM model owners and consumers can be achieved using AWS NitroTPM and EC2 instance attestation. This application runs on EC2 instances with NitroTPM enabled and uses Ollama with NVIDIA CUDA support. Note that EC2 instance attestation does work on a wide range on instance families including accelerated compute. Check out the README for some additional important details you should be aware of.

![architecture overview](https://raw.githubusercontent.com/aws-samples/sample-mpc-app-using-aws-nitrotpm/refs/heads/main/application_components.png)

### AWS and Community blog posts

**This weeks essential reading**

Here are the posts that I think are essential reads, so start here. We have more than we usually do, but thought these were all essential reads this month.

* [Best practices for migrating from Apache Airflow 2.x to Apache Airflow 3.x on Amazon MWAA](https://aws.amazon.com/blogs/big-data/best-practices-for-migrating-from-apache-airflow-2-x-to-apache-airflow-3-x-on-amazon-mwaa/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - explores the best practices for migrating from Apache Airflow 2.x to Apache Airflow 3.x on Amazon MWAA, highlighting key architectural improvements, breaking changes, and a streamlined approach to ensure a smooth transition while maximising the enhanced capabilities of Airflow 3 [hands on]
* [Introducing CLI Agent Orchestrator: Transforming Developer CLI Tools into a Multi-Agent Powerhouse](https://aws.amazon.com/blogs/opensource/introducing-cli-agent-orchestrator-transforming-developer-cli-tools-into-a-multi-agent-powerhouse/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - describes a new open source framework called CLI Agent Orchestrator (CAO,  pronounced “kay-oh) that transforms how developers work with AI powered CLI tools like Amazon Q CLI and Claude Code, enabling coordinated multi-agent workflows for complex software development, enterprise transformations, research and analysis, and quality assurance [hands on]

![cli agent orchestrator](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2025/10/07/cao_architecture-1024x428.png)

* [Using AWS Secrets Manager Agent with Amazon EKS](https://aws.amazon.com/blogs/security/using-aws-secrets-manager-agent-with-amazon-eks/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - looks at how the AWS Secrets Manager Agent can be deployed as a sidecar container in Amazon EKS to securely retrieve secrets from AWS Secrets Manager, addressing challenges around language-specific dependencies, network dependencies, and secret rotation [hands on]
* [Defending against supply chain attacks like Chalk/Debug and the Shai-Hulud worm](https://aws.amazon.com/blogs/security/defending-against-supply-chain-attacks-like-chalk-debug-and-the-shai-hulud-worm/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - explores two supply chain attacks, Chalk/Debug and the Shai-Hulud worm, that compromised popular open source packages to distribute malware and harvest credentials, highlighting the risks of relying on third-party dependencies

**Community**

Each month I spend time reading posts from across the AWS community on open source topics. In this section I share what personally caught my eye and interest, and I hope that many of you will also find them interesting. x

Starting us off this month is **Khawaja Shams** who looks at the latest Valkey 8.1 release that introduces optimisations that promises lower memory usage and higher throughput, and goes on to demonstrate this by showing what happens when you insert 50 million members into a sorted set,  benchmarking this against Valkey 8.0. No spoilers you will have to read the post, [How Valkey 8.1 Handles 50 Million Sorted Set Inserts](https://valkey.io/blog/50-million-zsets/). Sticking with Valkey we have **Ran Shidlansik** who shared [Introducing Hash Field Expirations with us](https://valkey.io/blog/hash-fields-expiration/) that explains how Valkey's new hash field expirations feature allows developers to set different expiration times for individual fields within a hash, providing more flexibility in managing data lifetimes without increasing the complexity of the system or impacting performance. The final Valkey related post comes from **Yunus** who shares nice cost and performance analysis between Redis and Valkey in his post, [AWS Elasticache: A Performance and Cost Analysis of Redis 7.1 vs. Valkey 7.2](https://builder.aws.com/content/33pPyndP8eIcjWJprmCQaRiDf70/aws-elasticache-a-performance-and-cost-analysis-of-redis-71-vs-valkey-72?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el).

**AWS Hero Kenta Goto** is up next with this post, [AWS CDK Unit Testing Guide: When and How to Use Different Test Types](https://dev.to/aws-heroes/aws-cdk-unit-testing-guide-when-and-how-to-use-different-test-types-331g) who shows us readers the three main types of unit tests in AWS CDK: snapshot tests, fine-grained assertions tests, and validation tests. He goes on to dive deep into these, looking at use cases and comparing each approach. Go check it out if you use AWS CDK. **AWS Community Builder Marko Štrukelj** (ServerlessLife) gives you more CDK goodness in the shape of his post on LinkedIn, [CDK Booster - Speeding Up Bundling of Lambda Handlers](https://www.linkedin.com/pulse/cdk-booster-speeding-up-bundling-lambda-handlers-serverlesslife--q3gde) an [open source project](https://github.com/ServerlessLife/cdk-booster) he created to speed up how CDK bundles TypeScript/JavaScript Lambda handlers, from sequential to all at once. Better still, its a drop in replacement, with just a tweak to your cdk.json. Defo something you should check out.

Next up is **haruki** who dives into the announcement this month of Fluent Bit 4.1.0 now being available within AWS for Fluent Bit 3.0.0 in his post, [AWS for Fluent Bit 3.0.0 Based on Fluent Bit 4.1.0](https://builder.aws.com/content/34DFtGMJZqLcbMv8erBliaMYa76/aws-for-fluent-bit-300-based-on-fluent-bit-410?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el). The post explores native OTLP support, faster JSON parsing, and enhanced security controls on Amazon Linux 2023 that eliminate the need for additional sidecar containers in your ECS and EKS environments.

To finish up this month we have my colleague **Elizabeth Fuentes** who has put together a really nice resource for speakers who regularly do talks at events and need to share resources with attendees. Check out [Building an Event Resources Website with AWS CDK and Amazon Q Developer CLI](https://builder.aws.com/content/347AT8mTyDtAQFkPxOEdjZjIvCU/building-an-event-resources-website-with-aws-cdk-and-amazon-q-developer-cli?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) for details on what this looks like, and Eli shares a code repo so you can quickly get started.

Thats all for this month. If you have an open source article you want to share with the community, drop me a message (LinkedIn, or via [ricsue@amazon.co.uk](mailto:ricsue@amazon.co.uk) and I will be sure to check it out.


**AI**

* [Building In-Vehicle AI Assistants with Strands Agents](https://aws.amazon.com/blogs/industries/building-in-vehicle-ai-assistants-with-amazon-strands-agents/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - shows off an in vehicle AI assistant architecture that leverages Strands Agents SDK, an open source framework for building agents, to handle various voice commands and provide intelligent, responsive, and personalised experiences for drivers [hands on]
* [Medical reports analysis dashboard using Amazon Bedrock, LangChain, and Streamlit](https://aws.amazon.com/blogs/machine-learning/medical-reports-analysis-dashboard-using-amazon-bedrock-langchain-and-streamlit/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - looks at a medical reports analysis dashboard that leverages Amazon Bedrock's advanced AI capabilities, LangChain's document processing, and Streamlit's user interface to help healthcare providers efficiently interpret complex medical data [hands on]

* [Configure and verify a distributed training cluster with AWS Deep Learning Containers on Amazon EKS](https://aws.amazon.com/blogs/machine-learning/configure-and-verify-a-distributed-training-cluster-with-aws-deep-learning-containers-on-amazon-eks/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - provides a step-by-step guide to configure and verify a distributed training cluster with AWS Deep Learning Containers on Amazon EKS, highlighting the importance of proper GPU and networking configuration for large-scale model training [hands on]


**Cloud Native**

* [Extending EKS with Hybrid Nodes: IAM Roles Anywhere and HashiCorp Vault](https://aws.amazon.com/blogs/containers/extending-eks-with-hybrid-nodes-iam-roles-anywhere-and-hashicorp-vault/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - is a post that shows how to use AWS Identity and Access Management (IAM) Roles Anywhere and Vault PKI, to facilitate joining Amazon EKS Hybrid Nodes to an Amazon EKS Cluster, enabling businesses to use compute resources outside of AWS [hands on]

![architecture overview](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2025/10/01/CONTAINERS-55-PKI-Arch.png)

* [How to manage EKS Pod Identities at scale using Argo CD and AWS ACK](https://aws.amazon.com/blogs/containers/how-to-manage-eks-pod-identities-at-scale-using-argo-cd-and-aws-ack/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - helps you understand how to manage EKS Pod Identities at scale using Argo CD and AWS ACK, exploring the benefits of the EKS Pod Identity feature and addressing the challenge of eventual consistency in the EKS Pod Identity API [hands on]
* [Assess compliance and configuration of Kubernetes resources with AWS Config](https://aws.amazon.com/blogs/mt/assess-compliance-and-configuration-of-kubernetes-resources-with-aws-config/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - provides a solution that extends AWS Config capabilities to record, track, and evaluate compliance of Kubernetes resources running within Amazon EKS clusters, providing a comprehensive view of both AWS and Kubernetes configurations [hands on]

* [Running Slurm on Amazon EKS with Slinky](https://aws.amazon.com/blogs/containers/running-slurm-on-amazon-eks-with-slinky/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - describes how the Slinky Project allows running Slurm, a popular workload manager and job scheduler, on Amazon EKS, providing the benefits of both Kubernetes and Slurm for AI infrastructure [hands on]

* [SaaS deployment architectures with Amazon EKS](https://aws.amazon.com/blogs/containers/saas-deployment-architectures-with-amazon-eks/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - outlines a SaaS deployment architecture using Amazon EKS that enables SaaS providers to offer deployment options within their customers' environments, providing data sovereignty, compliance, and performance benefits [hands on]

![SaaS Provider hosted model](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2025/10/10/arch-diagram-1.png)

* [Improve Kubernetes pod scheduling accuracy using Amazon EBS](https://aws.amazon.com/blogs/storage/improve-kubernetes-pod-scheduling-accuracy-using-amazon-ebs/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - looks at how the new Mutable CSI Node Allocatable Count feature in Amazon EKS 1.34 solves the challenge of inaccurate pod scheduling due to outdated volume attachment capacity information, enabling real-time capacity updates and automatic recovery from volume attachment failures [hands on]

* [New AWS whitepaper: Security Overview of Amazon EKS Auto Mode](https://aws.amazon.com/blogs/security/new-aws-whitepaper-security-overview-of-amazon-eks-auto-mode/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - provides essential reading, and looks at a new AWS whitepaper that provides an in-depth security overview of Amazon EKS Auto Mode, covering its architecture, built-in security features, and capabilities to help cloud architects, security professionals, and Kubernetes practitioners understand its security approach
* [Enhancing container security in Amazon EKS Auto Mode with KubeArmor](https://aws.amazon.com/blogs/containers/enhancing-container-security-in-amazon-eks-auto-mode-with-kubearmor/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - dives into how KubeArmor, an open source container security system, enhances the security of containerised workloads running on Amazon EKS Auto Mode by providing deep, system-call-level runtime protection and fine-grained policy enforcement
* [New Amazon EKS Auto Mode features for enhanced security, network control, and performance](https://aws.amazon.com/blogs/containers/new-amazon-eks-auto-mode-features-for-enhanced-security-network-control-and-performance/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - helps you understand the new Amazon EKS Auto Mode features that enhance security, network control, and performance by automating Kubernetes cluster management [hands on]

* [Implementing Disaster Recovery for Red Hat OpenShift workloads using CloudCasa and Red Hat OpenShift on AWS (ROSA)](https://aws.amazon.com/blogs/ibm-redhat/implementing-disaster-for-red-hat-openshift-workloads-using-cloudcasa-and-red-hat-openshift-on-aws-rosa/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - shares how Red Hat OpenShift and CloudCasa on AWS can simplify disaster recovery for containerised workloads, enabling streamlined backup and recovery operations across hybrid cloud environments

**Data and Analytics**

* [Announcing vector search for Amazon ElastiCache](https://aws.amazon.com/blogs/database/announcing-vector-search-for-amazon-elasticache/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - explains how Amazon ElastiCache now offers vector search capabilities, enabling high performance indexing, searching, and updating of billions of high-dimensional vector embeddings with low latency and high recall

* [Implement fine-grained access control for Iceberg tables using Amazon EMR on EKS integrated with AWS Lake Formation](https://aws.amazon.com/blogs/big-data/implement-fine-grained-access-control-for-iceberg-tables-using-amazon-emr-on-eks-integrated-with-aws-lake-formation/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - looks at how to implement fine grained access control for Iceberg tables using Amazon EMR on EKS integrated with AWS Lake Formation, enabling secure data sharing and governance in a data mesh architecture, particularly for sensitive data in domains like healthcare [hands on]

![high level design](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2025/10/03/bdb3741-1.png)

* [Monitoring multithreaded replication in Amazon RDS for MySQL, Amazon RDS for MariaDB, and Aurora MySQL](https://aws.amazon.com/blogs/database/monitoring-multithreaded-replication-in-amazon-rds-for-mysql-amazon-rds-for-mariadb-and-aurora-mysql/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - describes methods to effectively monitor parallel replication performance and tune related parameters for MySQL and MariaDB, including using the SHOW REPLICA STATUS command to understand replication status and lag [hands on]
* [Overview and best practices of multithreaded replication in Amazon RDS for MySQL, Amazon RDS for MariaDB, and Amazon Aurora MySQL](https://aws.amazon.com/blogs/database/overview-and-best-practices-of-multithreaded-replication-in-amazon-rds-for-mysql-amazon-rds-for-mariadb-and-amazon-aurora-mysql/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - dives deep into the key aspects of multithreaded replication in MySQL and MariaDB, including how it enhances binlog replication performance, its usefulness in modern operational practices, and the high-level architecture of MySQL replication with single-threaded replication
* [Performance optimization strategies for MySQL on Amazon RDS](https://aws.amazon.com/blogs/database/performance-optimization-strategies-for-mysql-on-amazon-rds/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - takes a look at strategies for optimising the performance of MySQL databases on Amazon RDS, including storage configuration, instance selection, and architectural decisions to improve query response times, resource utilisation, and cost-effectiveness [hands on]

* [Stream mainframe data to AWS in near real time with Precisely and Amazon MSK](https://aws.amazon.com/blogs/big-data/stream-mainframe-data-to-aws-in-near-real-time-with-precisely-and-amazon-msk/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - shares how Precisely and Amazon MSK enable enterprises to stream mainframe data to AWS in near real-time, addressing technical challenges like EBCDIC to ASCII conversion and handling complex VSAM file structures [hands on]

![solution architecture](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2025/10/03/BDB-4451-arch-diag.png)

* [Monitor Amazon Timestream for InfluxDB performance using the Timestream for InfluxDB Metrics dashboard](https://aws.amazon.com/blogs/database/monitor-amazon-timestream-for-influxdb-performance-using-the-timestream-for-influxdb-metrics-dashboard/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - is a solution that provides a dashboard that allows you to monitor the performance of your Amazon Timestream for InfluxDB databases, including the ability to perform trend analysis, create insights, set alerts, and automate reporting [hands on]

* [Search++, Going Beyond Keywords with Amazon OpenSearch Service](https://aws.amazon.com/blogs/big-data/search-going-beyond-keywords-with-amazon-opensearch-service/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - describes how organisations can enhance their existing search capabilities by integrating traditional relevancy algorithms with semantic understanding, leveraging language models and vector embeddings to better interpret user intent, handle natural language variations, and deliver more contextually relevant results [hands on]

**Other posts to check out**

* [Optimizing AWS development costs for .NET applications with LocalStack ](https://aws.amazon.com/blogs/dotnet/optimizing-aws-development-costs-for-net-applications-with-localstack/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el)- shows how LocalStack can help reduce development costs for .NET applications by running emulated AWS services locally, eliminating the need for reliable internet connectivity and AWS accounts during development and testing - if you haven't heard to used LocalStack, read this and then give it a go [hands on]
* [LibreOffice 64-bit progress, and support for Amazon Linux 2023](https://blog.documentfoundation.org/blog/2025/10/09/libreoffice-64-bit-progress-and-support-for-amazon-linux-2023/) - provides info about you can now use LibreOffice on Amazon Linux 2023, including how AWS is helping to support this effort
* [Announcing expanded support for Custom Slurm Settings in AWS Parallel Computing Service](https://aws.amazon.com/blogs/hpc/announcing-expanded-support-for-custom-slurm-settings-in-aws-parallel-computing-service/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - looks at the expanded support for custom Slurm settings in the AWS Parallel Computing Service, enabling users to configure and apply custom settings for greater scheduling control and alignment with on-premises HPC requirements

**Case Studies**

* [Hawk-Eye Innovations Powers Real-Time Sports Data with Flink and Amazon MSK](https://aws.amazon.com/blogs/media/hawk-eye-innovations-powers-real-time-sports-data-with-flink-and-amazon-msk/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - tells how Hawk-Eye Innovations, a Sony-owned company and AWS Strategic Partner, powers real-time sports data with Apache Flink and Amazon MSK to enable near real-time officiating decisions, immersive broadcast experiences, and performance optimisation for teams
* [GroundTruth reduces costs by 45% and improves reliability migrating from Aerospike to Amazon ElastiCache for Valkey](https://aws.amazon.com/blogs/database/groundtruth-reduces-costs-by-45-and-improves-reliability-migrating-from-aerospike-to-amazon-elasticache-for-valkey/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - this case study dives into how GroundTruth, an advertising platform, migrated from Aerospike to Valkey, reducing costs by 45% and improving reliability, while streamlining operations and enhancing performance
* [Infrastructure as Code at Thomson Reuters with AWS CDK](https://aws.amazon.com/blogs/devops/infrastructure-as-code-at-thomson-reuters-with-aws-cdk/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - looks at how Thomson Reuters developed an extension of the AWS Cloud Development Kit (CDK) to automate compliance, standardisation, and policy enforcement in Infrastructure as Code (IaC) scripts, and how it helped them to accelerate and standardise cloud infrastructure deployment and management
* [Beyond Bootstrap: Bootstrapless CDK Deployments at GoDaddy](https://aws.amazon.com/blogs/devops/beyond-bootstrap-bootstrapless-cdk-deployments-at-godaddy/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - provides a look at how GoDaddy evolved its AWS Cloud Development Kit (CDK) deployment process to enforce governance standards without compromising developer velocity, eliminating the explicit bootstrap step and creating a seamless, zero-touch experience
* [How Laravel Nightwatch handles billions of observability events in real time with Amazon MSK and ClickHouse Cloud](https://aws.amazon.com/blogs/big-data/how-laravel-nightwatch-handles-billions-of-observability-events-in-real-time-with-amazon-msk-and-clickhouse-cloud/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - describes how Laravel Nightwatch, a real-time observability platform built on AWS, handles billions of events per day using Amazon MSK and ClickHouse Cloud to provide developers with instant visibility into application performance


### Quick updates

**Amazon Corretto**

On October 21, 2025 Amazon announced quarterly security and critical updates for Amazon Corretto Long-Term Supported (LTS) versions of OpenJDK. Corretto 25.0.1, 21.0.9, 17.0.17, 11.0.29, 8u472 [are now available for download](https://aws.amazon.com/corretto/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el). Amazon Corretto is a no-cost, multi-platform, production-ready distribution of OpenJDK.

This release of Corretto JDK binaries for Generic Linux, Alpine and macOS will include Async-Profiler, a low overhead sampling profiler for Java supported by the Amazon Corretto team. Async-Profiler is designed to provide profiling data for CPU time, allocations in Java Heap, native memory allocations and leaks, contended locks, hardware and software performance counters like cache misses, page faults, context switches, Java method profiling, and much more.

**Apache Airflow**

Amazon Managed Workflows for Apache Airflow (MWAA) is a managed service for Apache Airflow that enables seamless workflow orchestration using the familiar Apache Airflow platform. It now supports Apache Airflow version 3.0, the latest major release of the workflow orchestration platform. This release enhances your ability to author, schedule, and monitor complex workflows with greater efficiency and control.

The availability of Apache Airflow v3.0 on MWAA introduces substantial improvements to workflow orchestration, including a completely redesigned interface for enhanced usability and advanced event-driven scheduling capabilities. This new scheduling system triggers workflows based on external events directly, eliminating the need for separate asset update pipelines. The newly introduced Task SDK in Apache Airflow v3.0 on MWAA help you simplify DAGs by reducing boilerplate code, making workflows more concise, readable, and consistent. Security and isolation are strengthened through the Task Execution API, which restricts direct access to the metadatabase and manages all runtime interactions. This release also features scheduler-managed backfill functionality, providing you better control over historical data processing. Additionally, MWAA now supports Python 3.12, while incorporating critical security improvements and bug fixes that enhance the overall reliability and security of your workflows in Amazon MWAA environments.

Find out more by reading the supporting blog post, [Introducing Apache Airflow 3 on Amazon MWAA: New features and capabilities](https://aws.amazon.com/blogs/big-data/introducing-apache-airflow-3-on-amazon-mwaa-new-features-and-capabilities/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el)

**InfluxDB**

Amazon Timestream for InfluxDB now offers support for InfluxDB 3. Now application developers and DevOps teams can run InfluxDB 3 databases as a managed service. InfluxDB 3 uses a new architecture for the InfluxDB database engine, built on Apache Arrow for in-memory data processing, Apache DataFusion for query execution, and columnar Parquet storage format with data persistence in Amazon S3 to deliver fast performance for high-cardinality data and large scale data processing for large analytical workloads.

With Amazon Timestream for InfluxDB 3, customers can leverage improved query performance and resource utilisation for data-intensive use cases while benefiting from virtually unlimited storage capacity through S3-based object storage. The service is available in two editions: Core, the open source version of InfluxDB 3, for near real-time workloads focused on recent data, and Enterprise for production workloads requiring high availability, multi-node deployments, and essential compaction capabilities for long-term storage. The Enterprise edition supports multi-node cluster configurations with up to 3 nodes initially, providing enhanced availability, improved performance for concurrent queries, and greater system resilience.

**Apache Kafka**

Amazon Managed Streaming for Apache Kafka (Amazon MSK) now supports Apache Kafka version 4.1, introducing Queues as a preview feature, a new Streams Rebalance Protocol in early access, and Eligible Leader Replicas (ELR). Along with these features, Apache Kafka version 4.1 includes various bug fixes and improvements. For more details, please refer to the Apache Kafka release notes for version 4.1. A key highlight of Kafka 4.1 is the introduction of Queues as a preview feature. Customers can use multiple consumers to process messages from the same topic partitions, improving parallelism and throughput for workloads that need point-to-point message delivery. The new Streams Rebalance Protocol builds upon Kafka 4.0's consumer rebalance protocol, extending broker coordination capabilities to Kafka Streams for optimixed task assignments and rebalancing. Additionally, ELR is now enabled by default to strengthen availability. To start using Apache Kafka 4.1 on Amazon MSK, simply select version 4.1.x when creating a new cluster via the AWS Management Console, AWS CLI, or AWS SDKs. You can also upgrade existing MSK provisioned clusters with an in-place rolling update. Amazon MSK orchestrates broker restarts to maintain availability and protect your data during the upgrade. 

**Apache Cassandra**

Amazon Keyspaces (for Apache Cassandra) is a scalable, highly available, and managed Apache Cassandra–compatible database service. Amazon Keyspaces is serverless, so you pay for only the resources that you use and you can build applications that serve thousands of requests per second with virtually unlimited throughput and storage. It now supports Internet Protocol version 6 (IPv6) through new dual-stack endpoints that enable both IPv6 and IPv4 connectivity. This enhancement provides customers with a vastly expanded address space while maintaining compatibility with existing IPv4-based applications. The dual-stack endpoints functionality allows you to gradually transition your applications from IPv4 to IPv6 without disruption, enabling safer migration paths for your critical database services. IPv6 support is also available through PrivateLink interface Virtual Private Cloud (VPC) endpoints, allowing you to access Amazon Keyspaces privately without traversing the public internet.

**AWS Serverless Application Model (SAM)**

AWS Serverless Application Model Command Line Interface (SAM CLI) now supports Finch as an alternative to Docker for local development and testing of serverless applications. This gives developers greater flexibility in choosing their preferred local development environment when working with SAM CLI to build and test their serverless applications.

Developers building serverless applications spend significant time in their local development environments. SAM CLI is a command-line tool for local development and testing of serverless applications. It allows you to build, test, debug, and package your serverless applications locally before deploying to AWS Cloud. To provide the local development and testing environment for your applications, SAM CLI uses a tool that can run containers on your local device. Previously, SAM CLI only supported Docker as the tool for running containers locally. Starting today, SAM CLI also supports Finch as a container development tool. Finch is an open-source tool, developed and supported by AWS, for local container development. This means you can now choose between Docker and Finch as your preferred container tool for local development when working with SAM CLI.

You can use SAM CLI to invoke Lambda functions locally, test API endpoints, and debug your serverless applications with the same experience you would have in the AWS Cloud. With Finch support, SAM CLI now automatically detects and uses Finch as the container development tool when Docker is not available. You can also set Finch as your preferred container tool for SAM CLI. This new feature supports all core SAM CLI commands including sam build, sam local invoke, sam local start-api, and sam local start-lambda.

**Kubernetes**

Kubernetes version 1.34 introduced several new features and bug fixes, and AWS is excited to announce that you can now use Amazon Elastic Kubernetes Service (EKS) and Amazon EKS Distro to run Kubernetes version 1.34. Starting today, you can create new EKS clusters using version 1.34 and upgrade existing clusters to version 1.34 using the EKS console, the eksctl command line interface, or through an infrastructure-as-code tool. Kubernetes version 1.34 introduces several key improvements, including projected service account tokens for kubelet image credential providers helping improve security for container image pulls, and Pod-level resource requests and limits for simplified multi-container resource management. The release also introduces Dynamic Resource Allocation (DRA) prioritised alternatives, enabling workloads to define prioritised device requirements for improved resource scheduling. To learn more about the changes in Kubernetes version 1.34, see our documentation and the Kubernetes project release notes. EKS now supports Kubernetes version 1.34 in all the AWS Regions where EKS is available, including the AWS GovCloud (US) Regions.

**Fluent Bit**

AWS for Fluent Bit enables Amazon ECS and Amazon EKS customers to collect, process, and route container logs to destinations including Amazon CloudWatch Logs, Amazon Data Firehose, Amazon Kinesis Data Streams, and Amazon S3 without changing application code. AWS for Fluent Bit announced version 3.0.0, based on Fluent Bit version 4.1.0 and Amazon Linux 2023. Container logging using AWS for Fluent Bit is now more performant and more feature-rich for AWS customers, including those using Amazon Elastic Container Services (Amazon ECS) and Amazon Elastic Kubernetes Service (Amazon EKS).

AWS for Fluent Bit 3.0.0 upgrades the Fluent Bit version to 4.1.0, and upgrades the base image to Amazon Linux 2023. These updates deliver access to the latest Fluent Bit features, significant performance improvements, and enhanced security. New features include native OpenTelemetry (OTel) support for ingesting and forwarding OTLP logs, metrics, and traces with AWS SigV4 authentication—eliminating the need for additional sidecars. Performance improvements include faster JSON parsing, processing more logs per vCPU with lower latency. Security enhancements include TLS min version and cipher controls, which enforce your TLS policy on outputs from AWS for Fluent Bit for stronger protocol posture.

You can use AWS for Fluent Bit 3.0.0 on both ECS and EKS. On ECS, update the FireLens log-router container image in your task definition to the 3.0.0 tag from the Amazon ECR Public Gallery. On EKS, upgrade by either updating the Helm release or setting the DaemonSet image to the 3.0.0 version.

**AWS ParallelCluster**

AWS ParallelCluster is a fully-supported and maintained open-source cluster management tool that enables R&D customers and their IT administrators to operate high-performance computing (HPC) clusters on AWS. ParallelCluster is designed to automatically and securely provision cloud resources into elastically-scaling HPC clusters capable of running scientific and engineering workloads at scale on AWS. AWS ParallelCluster 3.14 is now generally available. This release includes P6e-GB200 and P6-B200 instance types, prioritised allocation strategies for optimised instance placement, and NICE DCV support for Amazon Linux 2023. Other features included in this release are support for chef-client log visibility in instance console inside the instance's system log and Amazon Linux 2023 with kernel 6.12.

### Videos of the month

If you missed COMSUM, an amazing AWS Community run event held in Manchester every year in September, then the videos are now available on their YT channel. I have selected my favourite, and was lucky to chat with Ryan about Smithy and how cool this project is (and why the hell aren't more folks using it!). 

**Building Cloud-Native AI Agents with Strands: The Open Source SDK from AWS**

**Aaron Walker** introduces you to the core concepts behind Strands, including its plugin-based architecture for tools, memory, workflows, and more. He explores its native support for the Model Context Protocol (MCP) a powerful open standard for structuring and sharing contextual information with AI models. With MCP, agents gain deeper understanding, better grounding, and more reliable behaviour in enterprise environments.

{% youtube G-W_Fcuy8Jw %}

**APIs in the Fast Lane**

**AWS Community Builder Ryan Cormack** shares how design-first approaches using tools like Smithy and API Gateway can help keep your code, documentation, and SDKs in sync through code generation. He goes on to show you ways you can centrally manage gateways within clear domain boundaries to limit your attack surface. Finally he takes a look at practical strategies for migrating existing endpoints to a governed, managed service - all while enabling teams to move faster than ever before. Great session.

{% youtube mFtuTPgrFbA %}

**Build a Multi-Agent Role-Playing Game Master with Strands Agents**

My colleague  Tiffany Souterre shows you how to easily set up multi-agent workflows and tools using Strands Agents as she builds a really good RPG game. Dragons ahead, so tread carefully.

{% youtube Yp_go2ZWRWI %}

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes: Elizabeth Fuentes, haruki, Marko Štrukelj, Kenta Goto, Yunus, Ran Shidlansik, Khawaja Shams, Anurag Srivastava, Ankit Sahu, Kamen Sharlandjiev, Sriharsh Adari, Mohammad Sabeel, Satya Chikkala, Aditya Ranjan, Ahmed Elhosary, Alex Kestner, Aman Malkar, Ankit Sahu, Anuj Butail, Anurag Srivastava, Arun Gadila, Asif Khan, Brendan Bouffler, Chaitanya Nuthalapati, Charlie Bacon, Chenhe Liang, Chi Tran, Chris Clinton, Christoph Koerner, David Ho, Eddie Torres, Eric Anderson, Esther Querol Machado, Ezequiel Ballesteros, Felipe Lopez, Forest Vey, Francisco Morillo, G Buasai, Haofei Feng, Huy Nguyen, James Carpenter, Janakiraman Shanmugam, Jeetendra Vaidya, Jess Archer, Jinyan Li, Johnny Mirza, Jon Handler, Jonathan Hurley, Jordan Tauriainen, Juan Pablo Melgarejo Zamora, Kamen Sharlandjiev, Lucas Soriano Alves Duarte, Manasa Ramesh, Marc Reilly, Martin Guy Lapointe, Martin Phan, Marvin Gersho, Masudur Rahaman Sayem, Mathieu Bruneau, Meryem Ozcelik, Mike Ellis, Mukesh Agrawal, Nathan Arnold, Nirali Desai, Ohad Shacham, Prabhakaran Thatchinamoorthy, Prashant Agrawal, Pratik Yeole, Rahul Jadhav, Raj Reddy, Raj Seshadri, Rakesh Shirke, Ramkumar Ramanujam, Rishi Gera, Ronil Prasad, Roz Bennetts, Sajjan Gundapuneedi, Sanjay Chaudhari, Shubham Tiwari, Simone Pomata, Srini Raghavan, Steve Mirman, Sumanth Culli, Supreet Padhi, Tamara Astakhova, Tejal Patel, Tiago Reichert, Todd Neal, Tristan Poisson, Tsahi Duek, Tuan Nguyen, Venkat Devarajan, Venu Thangalapally, Vijai Thoppae, Vishal Jaswani, Vu San Ha Huynh, and Xun Gong


### Stay in touch with open source at AWS

Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) for more open source goodness.

One of the pieces of feedback I received was to create a repo where all the projects featured in this newsletter are listed. Where I can hear you all ask? Well as you ask so nicely, you can meander over to[ newsletter-oss-projects](https://github.com/094459/newsletter-oss-projects).

Made with ♥ from DevRel