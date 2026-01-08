---
title: 'AWS open source newsletter #216'
date: '2025-11-28'
tags : [ oss-newsletter, aws open source, Jupyter, Greengrass, Strands Agents, OpenTelemetry, Swift, Smithy, Kubernetes, Karpenter, Traefik, Kong Ingress Controller, Envoy, PostgreSQL, CDK, Grafana, Prometheus, Apache Kafka, Valkey, Cedar, Open Policy Agent, Rust, Python, ActiveMQ, RabbitMQ, AWS ParallelCluster, TiDB, Amazon EKS, Amazon Corretto, Apache Tomcat, Apache Airflow, MWAA, MySQL, MariaDB, Amazon EMR, Apache Spark, Amazon Linux, Mountpoint for Amazon S3, Lustre, Slurm, Ngnix, Stelvio, Jupyter Deploy, Apache Iceberg, Mem0 ]
canonicalUrl: "https://dev.to/aws/aws-open-source-newsletter-216-1c9p"
---


##  Edition #216 - November 2025

Welcome to issue #216 of the AWS open source newsletter, the newsletter where I try and provide you the best open source on AWS content.  re:Invent is just around the corner, and this months edition has a lot of great pre:Invent stuff, and I can't wait to see what other open source stuff gets announced. Some readers may be heading to re:Invent (or maybe already there), so enjoy the week. 

In this months edition we have a nice selection of projects from making it easier to use integrate with MCP Servers, a new Python framework that simplifies infrastructure management, managing credentials for local development, a couple of developer experience improvements for serverless developers, a new way to PySpark like code on Anthena, as well as the usual round up of cool demos and reference installations. Every month I am always impressed at how much cool stuff you all produce.

The projects will keep you busy until next month for sure, but we also have plenty of reading material in this months newsletter. In this edition we have featured projects that include Jupyter, Apache Iceberg, Greengrass, Strands Agents, OpenTelemetry, Swift, Smithy, Kubernetes, Karpenter, PostgreSQL, AWS CDK, Grafana, Prometheus, Apache Kafka, Valkey, Cedar, Open Policy Agent, Rust, Python, ActiveMQ, RabbitMQ, AWS ParallelCluster, TiDB, Amazon Corretto, Apache Tomcat, Apache Airflow, MySQL, MariaDB, Amazon EMR, Apache Spark, Amazon Linux, Mountpoint for Amazon S3, Lustre, Slurm, Ngnix, Stelvio, Mem0 , and Jupyter Deploy. Phew, that should keep you all very busy!

Check out the list of contributors at the end of the newsletter, and as always, get in touch if you want me to feature your projects in this open source newsletter. 

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution. The projects mentioned here do not represent any formal recommendation or endorsement, I am just sharing for greater awareness as I think they look useful and interesting!*

### Tools

**mcp-proxy-for-aws**

[mcp-proxy-for-aws](https://github.com/aws/mcp-proxy-for-aws) - is a new project that provides two ways to connect AI applications to MCP servers on AWS. The first is using it as a proxy, it becomes a lightweight, client-side bridge between MCP clients (AI assistants like Claude Desktop, Amazon Q Developer CLI) and MCP servers on AWS. The second is as a library, allowing you to programmatically connect popular AI agent frameworks (LangChain, LlamaIndex, Strands Agents, etc.) to MCP servers on AWS. If you are doing any kind of MCP stuff on AWS, this project is essential so make sure you try it out.

My colleague **Denis Traub** has put together a nice blog post on this really nice project, so go read [No OAuth Required: An MCP Client for IAM](https://builder.aws.com/content/35lOzB3OSseUt7omC6OdutPmrpk/no-oauth-required-an-mcp-client-for-iam?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el).

**stelvio**

[stelvio](https://github.com/stelviodev/stelvio) - is a Python framework that simplifies AWS cloud infrastructure management and deployment. It lets you define your cloud infrastructure using pure Python, with smart defaults that handle complex configuration automatically.

I recently had the delight of chatting with Bas Steins, one of the maintainers (and creators) of Stelvio. He shared a recent video where the maintainers explore the unique developer focused approach of Stelvio. How it compares to other tools, highlighting the features and components included in the latest release, and sharing insights on future developments, including the exciting Live Lambda feature. Additionally, they introduce the Early Explorer Program aimed at engaging the community and providing support for users trying out Stelvio in real-world applications.

{{< youtube hnqhxMoXGmo >}}

**credproxy**

[credproxy](https://github.com/JohnPreston/credproxy) is another awesome project from **John Preston**. credproxy provides a lightweight sidecar container that provides AWS credentials to applications using the same interface as ECS credential providers. Designed for local development and testing to strengthen applications that will later use AWS services like S3. The README provides a nice section on the problem that this project is trying to solve. What might that be I can hear you all saying? Applications often behave differently in local development vs production when using AWS SDKs, especially around credential management and AWS service integration.

Checkout the excellent README for more details and examples of how to get started.

**jupyter-deploy**

[jupyter-deploy](https://github.com/jupyter-infra/jupyter-deploy) is a new open source command line tool that simplifies deploying Jupyter applications to various cloud providers. Currently AWS is the only provider, but this will be added to over time. Check out the excellebt post from Jonathan Guinegagne and Danilo Poccia that provides the perfect primer - [Jupyter Deploy: Create a JupyterLab application with real-time collaboration in the cloud in minutes](https://aws.amazon.com/blogs/opensource/jupyter-deploy-create-a-jupyterlab-application-with-real-time-collaboration-in-the-cloud-in-minutes/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el).

![example notebook in the cloud](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2025/11/04/image-7-1024x832.png)

**cognitive-memory** 

[cognitive-memory](https://github.com/petertilsen/cognitive-memory) is a project from **Peter Tilsen** that builds a production-ready cognitive memory system for AI agents with human-like learning and memory patterns. It is easy to install and get up and running, and the docs have everything you need. [cognitive-memory-agent](https://github.com/petertilsen/cognitive-memory-agent)  provides a demo that showcases the cognitive-memory package, allowing you to see how agents learn, remember, and get smarter with each interaction.

**lambda-live-debugger**

[lambda-live-debugger](https://github.com/ServerlessLife/lambda-live-debugger) is an indispensable tool for debugging AWS Lambda functions from your computer, even though they are deployed in the cloud. The code runs with the same IAM permissions as in the cloud environment, and there's no need to redeploy when you make code changes. It supports Lambdas written in JavaScript or TypeScript. It requires almost no configuration. It supports a number of frameworks, so checkout this project for more details and how to get started. Marko is looking for feedback, so if you do try this out then please let him know what you think. Project also has a nice dedicate site which you can find at [https://www.lldebugger.com/](https://www.lldebugger.com/)

**aws-lambda-stubs**

[aws-lambda-stubs](https://github.com/cino/aws-lambda-stubs) is a new project from **AWS Community Builder Ricardo Cino** that provides simple stubs for AWS Lambda services, allowing you to focus on writing and testing your Lambda functions without the overhead of continuously writing the same boilerplate stubs. Gone are the days you need to write stubs to unit test your AWS Lambda functions locally. This project was inspired by @types/aws-lambda that already provides the type definitions for AWS Lambda events and context. There is support for all the typed AWS Lambda events defined in @types/aws-lambda and the project will be continuously updated as new event types are added. 

Ricardo has also put together this post,[ AWS Lambda Stubs for unit testing](https://dev.to/aws-builders/aws-lambda-stubs-for-unit-testing-96p), to walk you through this project.

**athena_bridge**

[athena_bridge](https://github.com/AlvaroMF83/athena_bridge) is an open-source Python library that replicates the most common PySpark functions, allowing you to execute PySpark-like code directly on AWS Athena via automatically generated SQL. With this library, you can reuse your existing PySpark code without needing an EMR Cluster or Glue Interactive Session, leveraging Athena’s SQL backend with identical syntax to PySpark.

**cloudformation-deployment-portal**

[cloudformation-deployment-portal](https://github.com/richardfan1126/cloudformation-deployment-portal) comes from **AWS Hero Richard Fan**, and is a new project that provides a web portal that allows administrators to deploy multiple CloudFormation stacks and provides public access to individual stack outputs using unique access codes. It allows Admins to deploy CloudFormation stacks through a web interface, with each deployment getting a unique UUID access code. Users can view their stack outputs by entering their UUID access code, whilst no authentication required for viewing outputs.

**cloud_shark**

[cloud_shark](https://github.com/andiggi/cloud_shark) is an open source project that helps you to keep track of your AWS spending trends. It sends cost summaries straight to your inbox, and runs entirely on AWS (Lambda + SNS + Cost Explorer). Check out the README, one potential gotcha is that you will need to have Pulumi CLI installed, but that is pretty straightforward.

**CDOps-Cloud-Zombie-Hunter**

[CDOps-Cloud-Zombie-Hunter](https://github.com/cdops-tech/CDOps-Cloud-Zombie-Hunter) is an open-source command-line utility that scans your AWS environment for unused resources—what we call "zombies"—that are quietly draining your budget. Check out the README for the list and kinds of resources within its cross hair, and before you panic, the tool is READ ONLY, so you still have to do some work finishing off those zombies. Poor zombies...always being finished off!

**greengrass-agent-context-pack**

[greengrass-agent-context-pack](https://github.com/aws-greengrass/greengrass-agent-context-pack) - this repo provides structured knowledge and step-by-step guides for AI agents to quickly set up and experiment with AWS IoT Greengrass Nucleus. It follows the https://agents.md specification, and will help streamline development workflows. Developers can boost productivity by cloning the repository and integrating it with modern generative AI tools like Amazon Q to help accelerate cloud-connected edge application development while simplifying fleet-wide deployment and management.


### Demos, Samples, Solutions and Workshops

**guidance-for-deploying-model-context-protocol-servers-on-aws**

[guidance-for-deploying-model-context-protocol-servers-on-aws](https://github.com/aws-solutions-library-samples/guidance-for-deploying-model-context-protocol-servers-on-aws) aside from being a contender for longest project name in this months round up, provides examples of how to securely run Model Context Protocol (MCP) servers on the AWS Cloud using containerised architecture. It helps organisations implement industry-standard OAuth 2.0 authentication while protecting server deployments with multiple security layers, including content delivery networks and web application firewalls.

You can read [How to deploy MCP Servers on AWS with the Best Practices](https://dev.to/aws-builders/how-to-deploy-mcp-servers-on-aws-with-the-best-practices-538) from **AWS Community Builder angelomao** who shares his experiences working with this project.

![overview of architecture](https://github.com/aws-solutions-library-samples/guidance-for-deploying-model-context-protocol-servers-on-aws/blob/main/assets/architecture-diagram.png?raw=true)

**multi-cloud-data-platform**

[multi-cloud-data-platform](https://github.com/adavoudi/multi-cloud-data-platform?tab=readme-ov-file) **Alireza Davoudi** has put together this repository contains an end-to-end data platform "playground" simulating a e-commerce marketplace. It's designed for data engineers to quickly experiment with various data engineering use cases in a semi-realistic environment. The architecture combines a local stack (Kafka, Debezium, MySQL) with cloud services. The primary goal is to provide a complete, replicable infrastructure setup for different cloud providers (starting with AWS). 

![overview of architecture for multi-cloud-data-platform](https://github.com/adavoudi/multi-cloud-data-platform/blob/main/assets/data-generators-2025-07-18-1404.png?raw=true)

**react-native-multi-tv-app-sample**

[react-native-multi-tv-app-sample](https://github.com/AmazonAppDev/react-native-multi-tv-app-sample) **Giovanni Laquidara** has shared this amazing repo which I have on my todo list to try out. Have you ever fancied trying to build an application you could host on your FireOS powered TV? I know I have, and so the news that Gio has put together a production ready TV application template built with React Native, that supports Android TV, Apple TV, Fire TV (with Fire OS), Fire TV (with Vega OS) and Web TV platforms is just what I wanted to hear. This monorepo showcases best practices for building cross-platform TV applications with shared UI components, efficient focus management, and platform-specific optimisations.

**strands-agents-semantic-summarizing-conversation-manager**

[strands-agents-semantic-summarizing-conversation-manager](https://github.com/danilop/strands-agents-semantic-summarizing-conversation-manager) this repo from my good friend **Danilo Poccia** provides a demonstration of a conversation management system for Strands Agents that combines summarisation with exact message recall using semantic search. As a prototype, this system demonstrates the core concepts but would benefit from additional hardening, testing, and optimization before production use. Danilo put together a must read post that explains some of the concepts behind this, which is required reading - go check it out -> [Never Forget a Thing: Building AI Agents with Hybrid Memory Using Strands Agents](https://dev.to/aws/never-forget-a-thing-building-ai-agents-with-hybrid-memory-using-strands-agents-2g66).

![overview of semantic summarise architecture](https://media2.dev.to/dynamic/image/width=800%2Cheight=%2Cfit=scale-down%2Cgravity=auto%2Cformat=auto/https%3A%2F%2Fdev-to-uploads.s3.amazonaws.com%2Fuploads%2Farticles%2Fpy6tl9spxm19mhzbkkkb.png)

**aws-terraform-starter-kit**

[aws-terraform-starter-kit](https://github.com/towardsthecloud/aws-terraform-starter-kit/) is a new repo from **AWS Community Builder Danny Steenman** that helps you bootstrap a production ready AWS Terraform starter kit with secure OIDC authentication, automated CI/CD, and security scanning that will help you deploy infrastructure in minutes. Check out the README that links to comprehensive documentation. 

In addition to this, Danny also shared two new cool github actions for terraform and cdk users that provide an infrastructure diff in your github PR before you deploy your changes, so go check them out here ->[terraform-plan-pr-commenter](https://github.com/marketplace/actions/terraform-plan-pr-commenter).
 
**aws-cdk-self-hosted-n8n-infra**
 
[aws-cdk-self-hosted-n8n-infra](https://github.com/azmimengu/aws-cdk-self-hosted-n8n-infra) this project provides a self-hosted N8N workflow automation platform deployment using AWS CDK. The architecture utilises N8N in queue mode to create a highly performant and scalable infrastructure.

**aws-java-cdk-setup**

[aws-java-cdk-setup](https://github.com/AdamBien/aws-java-cdk-setup) is a project from **AWS Hero Adam Bien** that provides a reference project on how to set yourself up for using AWS CDK in Java. He has a demo application ([aws-quarkus-lambda-function-url-cdk-plain](https://github.com/AdamBien/aws-quarkus-lambda-function-url-cdk-plain)) that you can study

**kinda-yunikarp**

[kinda-yunikarp](https://github.com/dacort/kinda-yunikarp) another project from the prolific **Damon Cortesi**. In his [own words](https://www.reddit.com/r/aws/comments/1p2h2s6/full_local_setup_for_testing_karpenter_autoscaling/) "I wanted to be able to do some testing of YuniKorn + Karpenter auto-scaling without paying the bill, so I created this setup script that installs them both in a local kind cluster with the KWOK provider and some "real-world" EC2 instance types. Once it's installed you can create new pods or just use the example deployments to see how YuniKorn and Karpenter respond to new resource requests. It also installs Grafana with a sample dashboard that shows basic stats round capacity requests vs. allocated and number of different instance types."

### AWS and Community blog posts

**This weeks essential reading**

Here are the posts that I think are essential reads, so start here. We have more than we usually do, but thought these were all essential reads this month.

* [Introducing Strands Agent SOPs ‚Natural Language Workflows for AI Agents](https://aws.amazon.com/blogs/opensource/introducing-strands-agent-sops-natural-language-workflows-for-ai-agents/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) -  describes a new approach called "Agent SOPs" that combines the flexibility of model driven AI agents with the control of code defined workflows, enabling teams to encode proven workflows into reusable natural language templates for intelligent automation [hands on]

* [AWS X-Ray SDKs/Daemon migration to OpenTelemetry](https://aws.amazon.com/blogs/mt/aws-x-ray-sdks-daemon-migration-to-opentelemetry/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - is something you should read if you are currently using AWS X-Ray SDKs as this is transitioning to the OpenTelemetry open source standard for application tracing, providing a unified format for instrumenting, generating, and exporting telemetry data

* [The Swift AWS Lambda Runtime moves to AWSLabs](https://aws.amazon.com/blogs/opensource/the-swift-aws-lambda-runtime-moves-to-awslabs/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - looks at the recent move of the Swift AWS Lambda Runtime project to the AWS Labs organisation, highlighting its origins in the Swift community and the benefits of using Swift for server-side development and AWS Lambda functions

**Community**

Each month I spend time reading posts from across the AWS community on open source topics. In this section I share what personally caught my eye and interest, and I hope that many of you will also find them interesting. x

Starting us off this month is **AWS Community Builder Ryan** writes about one of my favourite open source projects, Smithy in [Building the Smithy MCP](https://ryancormack.medium.com/building-the-smithy-mcp-3a33124b256d). Ryan walks you through how to build an MCP (Model Context Protocol) server for the Smithy language to provide LLMs (Large Language Models) with up to date and relevant information about Smithy concepts and documentation. My colleague **Laura Salinas** explores the architecture and patterns of multi-agent AI systems in her post, [Multi Agent Systems With Strands Agents](https://builder.aws.com/content/35neYGNjAiKPoUbwOWnMtczDzon/multi-agent-systems-with-strands-agents?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) where she explores foundational principles like orchestration and specialisation as well as looking at advanced patterns including Swarm, Workflow, Graph, Agents as Tools, and the groundbreaking A2A Protocol.

As it was a Kubecon month, I was expected a bunch of Kubernetes related posts and so first up is [Controlling Kubernetes Network Traffic Part One](https://builder.aws.com/content/35bjOw5tRBximj8q8MXku9X1qa3/controlling-kubernetes-network-traffic-part-1?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) from **AWS Community Builder Eyal Estrin** where he dives into network traffic flows within your Kubernetes clusters - there is a lot he covers, and its broader than just AWS stuff. From networking we move to infrastructure as code, and more specifically Terraform. **AWS Community Builder Oluwafemi Lawal** has put together [Navigating AWS EKS with Terraform: Configuring Karpenter for Just-in-Time Node Provisioning](https://dev.to/aws-builders/navigating-aws-eks-with-terraform-configuring-karpenter-for-just-in-time-node-provisioning-5g45) that demonstrates how to configure Amazon EKS with Karpenter via Terraform, and then walks you through some scale up and down scenarios. The last Kubernetes post comes from **Jagdeep** where he shows you how to build a production ready Reinforcement Learning from Human Feedback (RLHF) training platform on Amazon EKS that's simple, scalable and cost effective in the post, [Building a RLHF Training Platform on Amazon EKS](https://builder.aws.com/content/35l1sN5ewLqKVN6fU3lXQVlM9Zk/building-a-rlhf-training-platform-on-amazon-eks?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el).

Upgrade are potentially harrowing affairs, and I do enjoy reading a post where someone shares their experiences (and tips) so it was with great interest I read **AWS Community Builder Chanaka Supun**'s post [How I Upgraded RDS PostgreSQL Version From 13.20 to 17.6 ](https://dev.to/aws-builders/how-i-upgraded-rds-postgresql-version-from-1320-to-176-cgb). Lots of solid learnings in that post. From upgrades back to infrastructure as code, this time AWS CDK. **AWS Hero Kenta Goto** has not one but two posts. In [AWS CDK Unit Testing Advanced Tips: Aligning Feature Flags and Skipping Bundling](https://dev.to/aws-heroes/aws-cdk-unit-testing-advanced-tips-aligning-feature-flags-and-skipping-bundling-1fbk) he follows on from a previous post (featured in an earlier newsletter) and looks at some advanced tips for applying tests to your CDK stacks, specifically looking at feature flags and skip bundling. In his second post, [AWS CDK Introduces Mixins: A Major Feature for Flexible Construct Composition (Developer Preview)](https://dev.to/aws-heroes/aws-cdk-introduces-mixins-a-major-feature-for-flexible-construct-composition-developer-preview-583d) he looks at a new CDK feature (currently in developer preview) called Mixins. Mixins enables the partial application of abstractions to L1 Constructs or custom constructs that were traditionally done with L2 Constructs, allowing users to introduce only the features they need without using L2 Constructs. 

Thats all for this month. If you have an open source article you want to share with the community, drop me a message (LinkedIn, or via [ricsue@amazon.co.uk](mailto:ricsue@amazon.co.uk) and I will be sure to check it out.

**GenAI**

* [How Strands Agents brings geospatial generative AI to the public sector](https://aws.amazon.com/blogs/publicsector/how-strands-agents-brings-geospatial-generative-ai-to-the-public-sector/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - walks you through how Strands Agents can transform geospatial workflows, making spatial data accessible to government workers through natural language interactions, overcoming barriers of GIS expertise and inaccessible interfaces

![geospatial example of using strands agent](https://d2908q01vomqb2.cloudfront.net/9e6a55b6b4563e652a23be9d623ca5055c356940/2025/10/29/Picture42.png)

**Cloud Native**

* [Introducing the fully managed Amazon EKS MCP Server (preview)](https://aws.amazon.com/blogs/containers/introducing-the-fully-managed-amazon-eks-mcp-server-preview/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - describes a new fully managed Amazon EKS MCP Server that simplifies managing Kubernetes clusters through conversation, eliminating the need for deep Kubernetes expertise [hands on]

* [Data-driven Amazon EKS cost optimization: A practical guide to workload analysis](https://aws.amazon.com/blogs/containers/data-driven-amazon-eks-cost-optimization-a-practical-guide-to-workload-analysis/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) -  introduces some of the key considerations for optimizing Amazon Elastic Kubernetes Service (Amazon EKS) costs in production environments - and a great seg-way to the next post!
* [Using Kubernetes Labels to Split and Track Application Costs on Amazon EKS](https://aws.amazon.com/blogs/aws-cloud-financial-management/using-kubernetes-labels-to-split-and-track-application-costs-on-amazon-eks-2/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - provides a solution that enables users to leverage Kubernetes labels to split and track application costs on Amazon EKS, allowing for more granular cost allocation and visibility [hands on]

![example report splitting cost](https://d2908q01vomqb2.cloudfront.net/2e01e17467891f7c933dbaa00e1459d23db3fe4f/2025/10/28/image-9-4-1024x225.png)

* [Monitoring network performance on Amazon EKS using AWS Managed Open Source Services ](https://aws.amazon.com/blogs/containers/monitoring-network-performance-on-amazon-eks-using-aws-managed-open-source-services/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - shows you how to monitor network performance on Amazon EKS using open source technologies, including capturing network performance metrics and exporting them to services like Prometheus and Grafana [hands on]

![example grafana dashboard showing network activity](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2025/11/19/image-4-10.png)

* [Secure EKS clusters with the new support for Amazon EKS in AWS Backup](https://aws.amazon.com/blogs/aws/secure-eks-clusters-with-the-new-support-for-amazon-eks-in-aws-backup/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - looks at how the new support for Amazon EKS in AWS Backup provides a centralised, policy-driven solution to secure Kubernetes applications by protecting both cluster configurations and application data, eliminating the need for custom scripts and simplifying the restore process

* [Amazon EKS Blueprints for CDK: Now supporting Amazon EKS Auto Mode](https://aws.amazon.com/blogs/containers/amazon-eks-blueprints-for-cdk-now-supporting-amazon-eks-auto-mode/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - dives into how you can now use Amazon EKS Auto Mode within Amazon EKS Blueprints, an open source framework that helps you bootstrap and configure production ready Amazon EKS clusters using AWS CDK [hands on]

* [Enhancing and monitoring network performance when running ML Inference on Amazon EKS](https://aws.amazon.com/blogs/containers/enhancing-and-monitoring-network-performance-when-running-ml-inference-on-amazon-eks/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - outlines the importance of Container Network Observability for ML inference workloads, emphasising the critical need for low inference latency and some of the challenges teams encounter when optimising and troubleshooting these workloads [hands on]

**Data and Analytics**

* [Introducing catalog federation for Apache Iceberg tables in the AWS Glue Data Catalog](https://aws.amazon.com/blogs/big-data/introducing-catalog-federation-for-apache-iceberg-tables-in-the-aws-glue-data-catalog/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - explores how catalog federation addresses the growing challenge of managing Apache Iceberg tables across multi-vendor catalog environments [hands on]
* [Accelerate data lake operations with Apache Iceberg V3 deletion vectors and row lineage](https://aws.amazon.com/blogs/big-data/accelerate-data-lake-operations-with-apache-iceberg-v3-deletion-vectors-and-row-lineage/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - walks you through the new capabilities in Iceberg V3, explain how deletion vectors and row lineage help you manage some of the challenges with managing growing data lakes [hands on]
* [Getting started with Apache Iceberg write support in Amazon Redshift](https://aws.amazon.com/blogs/big-data/getting-started-with-apache-iceberg-write-support-in-amazon-redshift/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - shows how you can use Amazon Redshift to write data directly to Apache Iceberg tables stored in Amazon S3 and S3 Tables for seamless integration between your data warehouse and data lake while maintaining ACID compliance [hands on]

* [PostgreSQL as a JSON database: Advanced patterns and best practices](https://aws.amazon.com/blogs/database/postgresql-as-a-json-database-advanced-patterns-and-best-practices/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - is essential reading and shows how PostgreSQL's JSON capabilities make it a compelling alternative to NoSQL databases for handling adaptable data models in modern applications, with features like ACID compliance, advanced indexing, and seamless integration with AWS services [hands on]
* [AI-powered tuning tools for Amazon RDS for PostgreSQL and Amazon Aurora PostgreSQL databases: PI Reporter](https://aws.amazon.com/blogs/database/ai-powered-tuning-tools-for-amazon-rds-for-postgresql-and-amazon-aurora-postgresql-databases-pi-reporter/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - shares how an AI powered database tuning tool called PI Reporter can help monitor and optimise the performance of Amazon RDS for PostgreSQL and Amazon Aurora PostgreSQL databases by analysing key metrics and providing prescriptive recommendations [hands on]

![solution architecture overview](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2025/10/16/pi-2.png)

* [Improving throughput of serverless streaming workloads for Kafka ](https://aws.amazon.com/blogs/compute/improving-throughput-of-serverless-streaming-workloads-for-kafka/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - looks at how to optimise the throughput and scaling of serverless streaming workloads using AWS Lambda and Apache Kafka, exploring various optimisation techniques [hands on]

* [Build persistent memory for agentic AI applications with Mem0 Open Source, Amazon ElastiCache for Valkey, and Amazon Neptune Analytics](https://aws.amazon.com/blogs/database/build-persistent-memory-for-agentic-ai-applications-with-mem0-open-source-amazon-elasticache-for-valkey-and-amazon-neptune-analytics/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - announces a new integration between Mem0 Open Source, Amazon ElastiCache for Valkey, and Amazon Neptune Analytics to provide persistent memory capabilities to agentic AI applications [hands on]
* [Building secure Amazon ElastiCache for Valkey deployments with Terraform](https://aws.amazon.com/blogs/database/building-secure-amazon-elasticache-for-valkey-deployments-with-terraform/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - shares details on the serverless and node-based deployment options for ElastiCache for Valkey, highlighting the benefits and use cases for each approach [hands on]

![overview of architecture for deploying Valkey](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2025/10/31/DBBLOG-4861-2.png)

**Other posts to check out**

* [Migrating from Open Policy Agent to Amazon Verified Permissions](https://aws.amazon.com/blogs/security/migrating-from-open-policy-agent-to-amazon-verified-permissions/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - is just the post you need if you are looking to migrate from Open Policy Agent (OPA) to Amazon Verified Permissions - provides an overview of how that uses the Cedar policy language, offering improved performance, policy authoring, and formal verification capabilities while reducing operational overhead [hands on]

* [Building serverless applications with Rust on AWS Lambda](https://aws.amazon.com/blogs/compute/building-serverless-applications-with-rust-on-aws-lambda/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - looks at how to build serverless applications with Rust on AWS Lambda, including installing and configuring Cargo Lambda, creating a basic HTTP Lambda function, and building a complete serverless API using AWS CDK with Rust Lambda functions [hands on]

* [Build priority-based message processing with Amazon MQ and AWS App Runner](https://aws.amazon.com/blogs/architecture/build-priority-based-message-processing-with-amazon-mq-and-aws-app-runner/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - provides a walk through for a priority based message processing system using a bunch of open source and AWS managed Services [hands on]

![solution architecture for activemq](https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2025/11/13/image-1-2.jpeg)

* [High availability patterns for AWS IoT Greengrass using Pacemaker](https://aws.amazon.com/blogs/iot/high-availability-patterns-for-aws-iot-greengrass-using-pacemaker/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - describes a technical guide on implementing high availability patterns for AWS IoT Greengrass using the [Pacemaker](https://github.com/ClusterLabs/pacemaker) cluster resource manager, including active/passive and active/active configurations with automated failover, state replication, and monitoring integration [hands on]

* [Streamlining Multi-Account Infrastructure with AWS CloudFormation StackSets and AWS CDK](https://aws.amazon.com/blogs/devops/streamlining-multi-account-infrastructure-with-aws-cloudformation-stacksets-and-aws-cdk/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - covers how to streamline multi account infrastructure management on AWS using CloudFormation StackSets and AWS CDK, including implementing a robust CI/CD pipeline for automated deployments with AWS CodePipeline [hands on]

![solution overview](https://d2908q01vomqb2.cloudfront.net/7719a1c782a1ba91c031a682a0a2f8658209adbf/2025/11/03/StackSets-Page-2.drawio.png)

* [What's the difference between AWS ParallelCluster  and AWS Parallel Computing Service?](https://aws.amazon.com/blogs/hpc/thoughts-on-the-differences-between-aws-parallel-computing-service-and-aws-parallelcluster/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - looks at the key differences between AWS ParallelCluster (an open-source cluster management tool) and AWS Parallel Computing Service (PCS, a managed HPC environment)


**Case Studies**

* [How Alight Solutions achieved 60% cost savings with Amazon ElastiCache for Valkey](https://aws.amazon.com/blogs/database/how-alight-solutions-achieved-60-cost-savings-with-amazon-elasticache-for-valkey/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - shows how Alight Solutions achieved 60% cost savings by migrating their caching infrastructure to Amazon ElastiCache for Valkey

* [PingCAP increased TiDB Cloud stability using Amazon EBS detailed performance statistics](https://aws.amazon.com/blogs/storage/pingcap-increased-tidb-cloud-stability-using-amazon-ebs-detailed-performance-statistics/) - is a nice case study and technical deep dive on how TiDB, a popular open source time stream database, uses AWS servers to stay on top of critical performance indicators to make sure that quickly identify potential issues and take timely optimisation measures, significantly improving the end-user service experience for TiDB Cloud customers [hands on]

* [How Smarsh reduced costs and increased scale migrating from Pivotal Cloud Foundry to Amazon EKS](https://aws.amazon.com/blogs/migration-and-modernization/how-smarsh-reduced-costs-and-increased-scale-migrating-from-pivotal-cloud-foundry-to-amazon-eks/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) - shares how Smarsh, working with AWS Professional Services, migrated over 250 applications from Cloud Foundry to Amazon EKS in less than 10 months, achieving cost savings and improved scalability

![amazon eks architecture and solution overview](https://d2908q01vomqb2.cloudfront.net/1f1362ea41d1bc65be321c0a378a20159f9a26d0/2025/08/04/MIGMOD-461-image-2.png)

### Quick updates

**Amazon Corretto**

AWS Elastic Beanstalk now enables customers to build and deploy Java applications using Amazon Corretto 25 on Amazon Linux 2023 (AL2023) platform. This latest platform support allows developers to leverage the newest Java 25 features while benefiting from AL2023's enhanced security and performance capabilities. AWS Elastic Beanstalk is a service that provides the ability to deploy and manage applications in AWS without worrying about the infrastructure that runs those applications. Corretto 25 on AL2023 allows developers to take advantage of the latest Java language features including compact object headers, ahead-of-time (AOT) caching, and structured concurrency. Developers can create Elastic Beanstalk environments running Corretto 25 through the Elastic Beanstalk Console, CLI, or API.

**Apache Tomcat**

AWS Elastic Beanstalk now enables customers to build and deploy Tomcat 11 applications using Amazon Corretto 25 on Amazon Linux 2023 (AL2023) platform. This latest platform support allows developers to leverage the newest Java 25 and Jakarta EE 11 features while benefiting from AL2023's enhanced security and performance capabilities. AWS Elastic Beanstalk is a service that provides the ability to deploy and manage applications in AWS without worrying about the infrastructure that runs those applications. Tomcat 11 with Corretto 25 on AL2023 allows developers to take advantage of the latest Java language features including compact object headers, ahead-of-time (AOT) caching, and structured concurrency. Developers can create Elastic Beanstalk environments running Corretto 25 with Tomcat 11 on AL2023 through the Elastic Beanstalk Console, CLI, or API.

**Apache Airflow**

Amazon Managed Workflows for Apache Airflow (MWAA) now offers a serverless deployment option that eliminates the operational overhead of managing Apache Airflow environments while optimising costs through true serverless scaling. This new offering addresses key challenges that data engineers and DevOps teams face when orchestrating workflows: operational scalability, cost optimisation, and access management. Amazon MWAA Serverless provides seamless workflow orchestration with automatic resource provisioning and scaling. You can define workflows using either YAML configurations or Python-based DAGs, with support for over 80 AWS Operators from Apache Airflow v3.0. Each workflow runs in isolation with distinct AWS Identity and Access Management (IAM) permissions, ensuring secure access to AWS services and data. The service handles all infrastructure scaling automatically, with you paying only for the actual compute time used during task execution.

Check out [Introducing Amazon MWAA Serverless](https://aws.amazon.com/blogs/big-data/introducing-amazon-mwaa-serverless/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) that explores this new serverless deployment option.

**RabbitMQ**

Amazon MQ now supports RabbitMQ version 4.2 which introduces native support for the AMQP 1.0 protocol, a new Raft based metadata store named Khepri, local shovels, and message priorities for quorum queues. RabbitMQ 4.2 also includes various bug fixes and performance improvements for throughput and memory management. A key highlight of RabbitMQ 4.2 is the support of AMQP 1.0 as a core protocol offering enhanced features like modified outcome which allow consumers to modify message annotations before re-queueing or dead lettering, and granular flow control, which offers benefits including letting a client application dynamically adjust how many messages it wants to receive from a specific queue. Amazon MQ has also introduced configurable resource limits for RabbitMQ 4.2 brokers which you can modify based on your application requirements. Starting from RabbitMQ 4.0, mirroring of classic queues is no longer supported. Non-replicated classic queues are still supported. Quorum queues are the only replicated and durable queue type supported on RabbitMQ 4.2 brokers, and now offer message priorities in addition to consumer priorities.

In addition to the version update, Amazon MQ now supports LDAP (Lightweight Directory Access Protocol) authentication for RabbitMQ brokers in all available AWS regions. This feature enables RabbitMQ brokers to authenticate and authorize Amazon MQ users using identity providers which support LDAP, providing enhanced security and flexibility in access management. You can now authenticate your Amazon MQ users through the credentials stored in your LDAP server. You can also add, delete, and modify Amazon MQ users and assign permissions to topics and queues.

**PostgreSQL**

Some PostgreSQL version updates that you should know about this month:

* Amazon Relational Database Service (RDS) for PostgreSQL now supports the latest minor versions 17.7, 16.11, 15.15, 14.20, and 13.23. We recommend that you upgrade to the latest minor versions to fix known security vulnerabilities in prior versions of PostgreSQL, and to benefit from the bug fixes added by the PostgreSQL community. This release includes the new pgcollection extension for RDS PostgreSQL versions 15.15 and above (16.11 and 17.7). This extension enhances database performance by providing an efficient way to store and manage key-value pairs within PostgreSQL functions. Collections maintain the order of entries and can store various types of PostgreSQL data, making them useful for applications that need fast, in-memory data processing. The release also includes updates to extensions, with pg_tle upgraded to version 1.5.2 and H3_PG upgraded to version 4.2.3.

* Amazon RDS for PostgreSQL now supports major version 18, starting with PostgreSQL version 18.1. PostgreSQL 18 introduces several important community updates that improve query performance and database management. PostgreSQL 18.0 includes "skip scan" support for multicolumn B-tree indexes and improved WHERE clause handling for OR and IN conditions enhance query optimisation. Parallel Generalised Inverted Index (GIN) builds and updated join operations boost overall database performance. The introduction of Universally Unique Identifiers Version 7 (UUIDv7) combines timestamp-based ordering with traditional UUID uniqueness, particularly beneficial for high-throughput distributed systems. PostgreSQL 18 also improves observability by providing buffer usage counts, index lookup statistics during query execution, and per-connection I/O utilisation metrics. This release also includes support for the new pgcollection extension, and updates to existing extensions such as pgaudit 18.0, pgvector 0.8.1, pg_cron 1.6.7, pg_tle 1.5.2, mysql_fdw 2.9.3, and tds_fdw 2.0.5.

* Amazon Aurora PostgreSQL-Compatible Edition has added support for PostgreSQL versions 17.6, 16.10, 15.14, 14.19, and 13.22. The update includes the PostgreSQL community's product improvements and bug fixes, and also includes Aurora-specific enhancements. Dynamic Data Masking (DDM) (16.10 and 17.6 only) is a new database-level security feature that protects sensitive data like personally identifiable information by masking column values dynamically at query time based on role-based policies, without altering the actual stored data. This release also includes a shared plan cache, improved performance and recovery-time-objective (RTO) and improvement for Global Database switchovers.

**MySQL**

Not to be left out, MySQL also had some important version updates this month.

* Amazon Aurora MySQL - Compatible Edition 3 (with MySQL 8.0 compatibility) now supports MySQL 8.0.43 through Aurora MySQL v3.11. In addition to several security enhancements and bug fixes, MySQL 8.0.43 contains additional errors for group replication and introduces the mysql client “commands” option, which enables or disables most mysql client commands.

* Amazon RDS for MySQL now supports MySQL minor versions 8.0.44 and 8.4.7, the latest minors released by the MySQL community. We recommend upgrading to the newer minor versions to fix known security vulnerabilities in prior versions of MySQL and to benefit from bug fixes, performance improvements, and new functionality added by the MySQL community. Learn more about the enhancements in RDS for MySQL 8.0.44 and 8.4.7 in the Amazon RDS user guide.

**MariaDB**

Amazon Relational Database Service (Amazon RDS) for MariaDB now supports community MariaDB minor versions 10.6.24, 10.11.15, and 11.4.9. We recommend that you upgrade to the latest minor versions to fix known security vulnerabilities in prior versions of MariaDB, and to benefit from the bug fixes, performance improvements, and new functionality added by the MariaDB community.

**Apache Kafka**

Amazon Managed Streaming for Apache Kafka (Amazon MSK) now supports viewing topics directly through the Amazon MSK console, making it easier to inspect all your Kafka topics without setting up Kafka admin clients. You can browse and search topics within a cluster, quickly review replication settings and partition counts, and drill into individual topics to examine detailed configuration, partition-level information, and metrics. These console capabilities are powered by three new MSK APIs, ListTopics, DescribeTopic, and DescribeTopicPartitions that you can also use directly for programmatic access. The ListTopics API returns the list of all topics in a cluster, while the DescribeTopic and DescribeTopicPartitions APIs provide detailed configuration and partition information for a topic. All three APIs are available through the AWS CLI and AWS SDKs.

In addition to this update, was news that all new Amazon MSK Provisioned clusters with Express brokers will support Intelligent Rebalancing at no additional cost. This new capability makes it effortless for customers to execute automatic partition balancing operations when scaling their Kafka clusters up or down. Intelligent Rebalancing maximises the capacity utilisation of MSK Express-based clusters by optimally rebalancing Kafka resources on them for better performance, eliminating the need for customers to manage partitions themselves or via third-party tools. Intelligent Rebalancing performs these operations up to 180 times faster compared to Standard brokers. MSK Express brokers are designed to deliver up to three times more throughput per-broker, scale up to 20 times faster, and reduce recovery time by 90 percent as compared to Standard brokers running Apache Kafka. 

There is a great blog post that looks at this in more details, so go check it out -[ Amazon MSK Express brokers now support Intelligent Rebalancing for 180 times faster operation performance](https://aws.amazon.com/blogs/big-data/amazon-msk-express-brokers-now-support-intelligent-rebalancing-for-180-times-faster-operation-performance/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el) 

![example rebalancing graph](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2025/11/08/BDB-5269-1.png)

**Amazon EMR**

Amazon EMR 7.12 is now available featuring the new Apache Iceberg v3 table format with Apache Iceberg 1.10. This release enables you to reduce costs when deleting data, strengthen governance and compliance through better tracking for row level changes, and enhance data security with more granular data access control.  With Iceberg v3, you can delete data cost-effectively because Iceberg v3 marks deleted rows without rewriting entire files - speeding up your data pipelines while reducing storage costs. You get better governance and compliance capabilities through automatic tracking of every row’s creation and modification history, creating the audit trails needed for regulatory requirements and change data capture. You can enhance data security with table-level encryption, helping you meet privacy regulations for your most sensitive data. With Apache Spark 3.5.6 included in this release, you can leverage these Iceberg 1.10 capabilities for building robust data lakehouse architectures on Amazon S3. This release also includes support for data governance operations across your Iceberg tables using AWS Lake Formation. In addition, this release also includes Apache Trino 476.

**Apache Spark**

Amazon EMR Serverless now supports Apache Spark 4.0.1 (preview). With Spark 4.0.1, you can build and maintain data pipelines more easily with ANSI SQL and VARIANT data types, strengthen compliance and governance frameworks with Apache Iceberg v3 table format, and deploy new real-time applications faster with enhanced streaming capabilities. This enables your teams to reduce technical debt and iterate more quickly, while ensuring data accuracy and consistency. With Spark 4.0.1, you can build data pipelines with standard ANSI SQL, making it accessible to a larger set of users who don't know programming languages like Python or Scala. Spark 4.0.1 natively supports JSON and semi-structured data through VARIANT data types, providing flexibility for handling diverse data formats.

**Kubernetes**

There were a number of announcements, no doubt thanks to KubeCon.

First up was news of the general availability of the AWS Secrets Store CSI Driver provider EKS add-on. This new integration allows customers to retrieve secrets from AWS Secrets Manager and parameters from AWS Systems Manager Parameter Store and mount them as files on their Kubernetes clusters running on Amazon Elastic Kubernetes Service (Amazon EKS). The add-on installs and manages the AWS provider for the Secrets Store CSI Driver. With the new Amazon EKS add-on, customers can quickly and easily set up new and existing clusters using automation to leverage AWS Secrets Manager and AWS Systems Manager Parameter Store, enhancing security and simplifying secrets management. Amazon EKS add-ons are curated extensions that automate the installation, configuration, and lifecycle management of operational software for Kubernetes clusters, simplifying the process of maintaining cluster functionality and security.

There is a great post that will help you get started with this, so if you like the sounds of the update, go read [How to use the Secrets Store CSI Driver provider Amazon EKS add-on with Secrets Manager](https://aws.amazon.com/blogs/security/how-to-use-the-secrets-store-csi-driver-provider-amazon-eks-add-on-with-secrets-manager/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el)


Amazon EKS also introduced Provisioned Control Plane, a new feature that gives you the ability to select your cluster's control plane capacity to ensure predictable, high performance for the most demanding workloads. With Provisioned Control Plane, you can pre-provision the desired control plane capacity from a set of well-defined scaling tiers, ensuring the control plane is always ready to handle traffic spikes or unpredictable bursts. These new scaling tiers unlock significantly higher cluster performance and scalability, allowing you to run ultra-scale workloads in a single cluster.

**Greengrass**

AWS announced the release of AWS IoT Greengrass v2.16, introducing new core components for nucleus and nucleus lite. AWS IoT Greengrass is an Internet of Things (IoT) edge runtime and cloud service that helps customers build, deploy, and manage device software at the edge. The latest version 2.16 release includes enhanced debugging capabilities through the system log forwarder component. This component uploads system log files to AWS Cloud Watch, making it easier for developers to troubleshoot IoT edge applications.

The AWS IoT Greengrass v2.16 release also features a new nucleus lite version (v2.3) with TPM2.0 specification support, enabling developers to manage edge device security for their resource constrained devices using hardware-based root of trust modules. The implementation helps developers to scale their IoT deployments with confidence while providing secure storage for secrets and streamlined device authentication.

**Python**

WS Lambda now supports creating serverless applications using Python 3.14. Developers can use Python 3.14 as both a managed runtime and a container base image, and AWS will automatically apply updates to the managed runtime and base image as they become available. Python 3.14 is the latest long-term support release of Python. This release provides Lambda customers access to the latest Python 3.14 language features. You can use Python 3.14 with Lambda@Edge (in supported Regions), allowing you to customise low latency content delivered through Amazon CloudFront. Powertools for AWS Lambda (Python), a developer toolkit to implement serverless best practices and increase developer velocity, also supports Python 3.14. You can use the full range of AWS deployment tools, including the Lambda console, AWS CLI, AWS Serverless Application Model (AWS SAM), AWS CDK, and AWS CloudFormation to deploy and manage serverless applications written in Python 3.14.

To dive deeper into this, check out the blog post, [Python 3.14 runtime now available in AWS Lambda](https://aws.amazon.com/blogs/compute/python-3-14-runtime-now-available-in-aws-lambda/?trk=71546b8e-c969-4ead-aa9f-9cd06f6d8610&sc_channel=el)  that highlights new language features, runtime updates, and how developers can leverage the new runtime for building serverless applications.

**Amazon Linux**

AWS announced the general availability of Supplementary Packages for Amazon Linux (SPAL), a dedicated repository that provides developers and system administrators with streamlined access to thousands of pre-built, EPEL9 packages compatible for Amazon Linux 2023 (AL2023). Amazon Linux serves as the foundation for countless applications running on AWS, but developers often face lengthy processes when building packages from source code. SPAL addresses this challenge by offering ready-to-use packages that accelerate development workflows for teams working with AL2023 environments.

With SPAL, development teams can significantly reduce deployment times and focus on core application development rather than package compilation. This solution is particularly valuable for DevOps engineers, system administrators, and developers who need reliable packages for production workloads without the overhead of building from source. SPAL packages are derived from the community-maintained EPEL9 project, with AWS providing security patches as they become available upstream.

**Mountpoint for Amazon S3**

You can now monitor Mountpoint operations in observability tools such as Amazon CloudWatch, Prometheus, and Grafana. With this launch, Mountpoint emits near real-time metrics such as request count or request latency using OpenTelemetry Protocol (OTLP), an open source data transmission protocol. This means you can use applications such as CloudWatch agent or the OpenTelemetry (OTel) collector to publish the metrics into observability tools and create dashboards for monitoring and troubleshooting.

Previously, Mountpoint emitted operational data into log files, and you needed to create custom tools to parse the log files for insights. Now, when you mount your Amazon S3 bucket, you can configure Mountpoint to publish the metrics to an observability tool to proactively monitor issues that might impact your applications. For example, you can check if an application is unable to access S3 due to permission issues by analyzing the S3 request error metric that provides error types at an Amazon EC2 instance granularity.

**Lustre**

Amazon FSx for Lustre now delivers up to 5x faster directory listing (ls) performance, allowing you to browse and analyse the contents of your file systems more efficiently. Amazon FSx for Lustre is a high-performance, cost-effective, and scalable file storage service for compute-intensive workloads like machine learning training, financial analytics, and high-performance computing. ML researchers, data scientists, and developers who use FSx for Lustre for compute-intensive workloads commonly use their file systems to store data for interactive use cases like home directories and source code repositories. Today's performance improvement makes FSx for Lustre even faster for these interactive use cases by reducing the time it takes to list and analyse the contents of directories using "ls". The performance improvements are supported with the latest Lustre 2.15 client in all AWS regions where FSx for Lustre is available.

**Slurm**

AWS Parallel Computing Service (AWS PCS) now supports the Slurm REST API. This new feature enables you to programmatically submit jobs, monitor cluster status, and manage resources using HTTP requests instead of relying on command-line tools. AWS PCS is a managed service that makes it easier for you to run and scale your high performance computing (HPC) workloads and build scientific and engineering models on AWS using Slurm. The Slurm REST API helps you automate cluster operations and integrate HPC resources into existing systems and workflows, including web portals, CI/CD pipelines, and data processing frameworks, all without the overhead of maintaining additional REST API infrastructure.

**Nginx**

Amazon Lightsail now offers a new Nginx blueprint. This new blueprint has Instance Metadata Service Version 2 (IMDSv2) enforced by default, and supports IPv6-only instances. With just a few clicks, you can create a Lightsail virtual private server (VPS) of your preferred size that comes with Nginx preinstalled.

### Videos of the month

**Getting Started with Strands Agents: From First Agent to Production-Ready**

This comprehensive tutorial guides you through the Strands Agents SDK, an open-source framework for building powerful and production-ready AI agents. In this video, we'll take you from the basics of creating your first agent to advanced topics like multi-agent communication and performance evaluation. Learn how to connect your agents to various large language model providers, integrate with AWS services, and leverage tools like the Model Context Protocol (MCP) to extend their capabilities. By the end of this course, you'll have the skills to build, monitor, and evaluate your own AI agents for a wide range of applications.

{{< youtube 28uCH7BcSA4 >}}

**How to Build AI Agents with Strands**

A stellar cast (Damian Karlson, Chris Williams, Shala, and Du'an Lightfoot) in this vBrownBag take Strands Agent for a drive. Strands Agent is an open-source SDK developed by AWS for building autonomous AI agents using a model-driven approach. The framework is designed to make it easy for developers to create, test, and deploy agents that use large language models (LLMs) to plan, reason, and act with minimal code required.

{{< youtube oitnXSZbhXg >}}

**Jupyter Deploy: An Open-source CLI To Deploy Jupyter Securely To the Cloud**

Jonathan Guinegagne introduces a new open source CLI to deploy Jupyter to the cloud provider of your choice in a few minutes. Jupyter Deploy gives you a domain with encrypted HTTP (TLS), GitHub OAuth integration, real-time-collaboration, and fast UV-based environments. Like the rest of Jupyter, the Jupyter Deploy CLI is vendor neutral. Once you have deployed your Jupyter server, you can quickly share it with others as a public URL authenticated through GitHub.

{{< youtube NSG0HIz3tS0 >}}

**Why AWS chose Apache Airflow to power workflows for the next generation of Amazon SageMaker**

John Jackson and Kamen Sharlandjiev presented at the Airflow Summit recently, talking about Apache Airflow is integrated as part of Amazon SageMaker Unified Studio. They go into details around the motivations for choosing Airflow for this capability, the challenges with incorporating Airflow into such a large and diverse experience, the key role that open-source plays, how we’re leveraging GenAI to make that open source development experience better, and the goals for the future of Airflow in SageMaker Unified Studio. 

{{< youtube V3UYYQ_O1cc >}}

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes: Ajit Tandale, Alexander Vladimirov, Andreas Holt, Angel Zarramera, Anton Aleksandrov, Aritra Nag, Ashok Srirama, Avijit Goswami, Aychin Gasimov, Brendan Bouffler, Carlos Santana, Danilo Poccia, Darko Mesaros, Elamaran Shanmugam, Ezat Karimi, Franco Abregu, George John, HariKrishna Boorgadda, Idriss Laouali Abdou, James Hood, Jihed Mselmi, John Jackson, Jonathan Guinegagne, Jonathan Lee, Josh Loberant, Julian Wood, Kiran Lakkireddy, Krishna Reddy, Leandro Cavalcante Damascena, Manoj Jayadevan, Masudur Rahaman Sayem, Mihir Surani, Naina Thangaraj, Nicholas Clegg, Puneeth Komaragiri, Regis Fadzi Muchemwa, Sachin Khanna, Sachin Kotwal, Samuel Folkes, Shakhi Hali, Siddhant Srivastava, Sourav Kundu, Swapna Bandla, Sébastien Stormacq, Udi Dahan, Utsab Roy, Veliswa Boya, Vipin Garg, Yamini Pradeepika Rathamsetty, Yong JI, Bas Steins, Damian Karlson, Chris Williams, Shala, Du'an Lightfoot, Jonathan Guinegagne, John Jackson and Kamen Sharlandjiev 

### Stay in touch with open source at AWS

Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) for more open source goodness.

One of the pieces of feedback I received was to create a repo where all the projects featured in this newsletter are listed. Where I can hear you all ask? Well as you ask so nicely, you can meander over to[ newsletter-oss-projects](https://github.com/094459/newsletter-oss-projects).

Made with ♥ from DevRel