---
title: 'AWS open source newsletter #217'
date: '2025-12-18'
tags : [ oss-newsletter, aws open source, Strands Agents, Cedar, MCP, Spring AI, Aperf, openCypher, Mem0, AWS CDK, ArgoCD, Amazon EKS, Kubernetes, Red Hat Open Shift, Prometheus, Apache Spark, Apache Hive, Supabase, Apache Iceberg, Wordpress, OpenZFS, Razor, MLflow, PostgreSQL, Qiskit, Amazon Linux 2023, kro, Valkey, Backstage ]
canonicalUrl: "https://dev.to/aws/aws-open-source-newsletter-217-o44"
---


##  Edition #217 - December 2025

Welcome to the Christmas edition of the AWS open source newsletter, #217. I am publishing this before the end of the month as I begin to wind down and get ready for the holidays. We have plenty of gifts from the open source community to keep you busy over the festive period, and we have a bumper selection of projects. There are too many good ones to single out, so go check them out and let me know which ones you tried and liked.

The projects will keep you busy until next month for sure, but we also have plenty of reading material in this months newsletter. In this edition we have featured projects that include Strands Agents, Cedar, MCP, Spring AI, Aperf, openCypher, Mem0, AWS CDK, ArgoCD, Kubernetes, Red Hat Open Shift, Prometheus, Apache Spark, Apache Hive, Supabase, Apache Iceberg, Wordpress, OpenZFS, Razor, MLflow, PostgreSQL, Qiskit, Amazon Linux 2023, kro, Valkey, and Backstage . That should keep you all very busy!

Check out the list of contributors at the end of the newsletter, and as always, get in touch if you want me to feature your projects in this open source newsletter. 

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution. The projects mentioned here do not represent any formal recommendation or endorsement, I am just sharing for greater awareness as I think they look useful and interesting!*

### Tools

**sample-agentic-attack-tree-generator**

[sample-agentic-attack-tree-generator](https://github.com/aws-samples/sample-agentic-attack-tree-generator) is an AI-powered threat modeling platform built on Strands Framework. It automatically generates comprehensive attack trees from your project documentation and threat models, mapping them to MITRE ATT&CK techniques with actionable mitigation strategies.

![demo video](https://aws-samples.github.io/sample-agentic-attack-tree-generator/assets/images/InteractiveDashboardOutputWalkthrough.gif)

This is on my todo list over the holidays to check out.

**aidlc-workflows**

[aidlc-workflows](https://github.com/awslabs/aidlc-workflows) is an interesting new framework for intelligent software development workflow that adapts to your needs, maintains quality standards, and keeps you in control of the process. You can use to re-imagine your software development life cycle, taking a step back and providing you with an extensible and customisable framework. I spent a couple of weeks with this back in October, and found it both flexible and powerful enough to produce very good results on a number of example use cases. Check out the supporting blog post, [Open-Sourcing Adaptive Workflows for AI-Driven Development Life Cycle (AI-DLC)](https://aws.amazon.com/blogs/devops/open-sourcing-adaptive-workflows-for-ai-driven-development-life-cycle-ai-dlc/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) and [Building with AI-DLC using Amazon Q Developer](https://aws.amazon.com/blogs/devops/building-with-ai-dlc-using-amazon-q-developer/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) for more details.

![AI-DLC framework overview](https://d2908q01vomqb2.cloudfront.net/7719a1c782a1ba91c031a682a0a2f8658209adbf/2025/11/24/01_AI-DLC_workflow-1.png)

**ml-container-creator**

[ml-container-creator](https://github.com/awslabs/ml-container-creator) is a new project that helps reduce the complexity of creating your own container images that you can deploy on Amazon SageMaker using the Bring Your Own Container (BYOC) approach. This gives you full control over your model's runtime environment while leveraging SageMaker's managed infrastructure for hosting and scaling. Every generated project includes: SageMaker-compatible container with health checks and invocation endpoints, local testing suite to validate before deployment, sample model and training code to illustrate the deployment, AWS deployment scripts for ECR and SageMaker, and multi-framework support (sklearn, XGBoost, TensorFlow, vLLM, SGLang). The documentation is top class, so if this sounds interesting, go check out the [Getting Started Guide](https://awslabs.github.io/ml-container-creator/getting-started/).

**bedrock-agentcore-sdk-typescript**

[bedrock-agentcore-sdk-typescript](https://github.com/aws/bedrock-agentcore-sdk-typescript) is the official repo for the Amazon Bedrock AgentCore SDK in TypeScript. Amazon Bedrock AgentCore enables you to deploy and operate highly effective agents securely, at scale using any framework and model. With Amazon Bedrock AgentCore, developers can accelerate AI agents into production with the scale, reliability, and security, critical to real-world deployment. AgentCore provides tools and capabilities to make agents more effective and capable, purpose-built infrastructure to securely scale agents, and controls to operate trustworthy agents. Amazon Bedrock AgentCore services are composable and work with popular open-source frameworks and any model, so you don’t have to choose between open-source flexibility and enterprise-grade security and reliability.

**arch-navigator**

[arch-navigator](https://github.com/awslabs/arch-navigator) is an open source desktop application that helps cloud builders navigate and understand their infrastructure. It provides a simple tree view of AWS resources and their relationships using existing APIs. Browse, inspect, and understand relationships between resources across AWS and other cloud providers.

The repo provides details of how to get this project up and running, as well as the resources currently supported. Go check it out and let them know what you think. Project is at an early stage, so take that into consideration when exploring.

**bedrock-usage-analyzer**

[bedrock-usage-analyzer](https://github.com/awslabs/bedrock-usage-analyzer) this CLI tool visualises foundation model (FM) usage in Amazon Bedrock. It calculates the tokens-per-minute/TPM and requests-per-minute/RPM. It also aggregates the FM usage across Bedrock application inference profiles and provides visibility on current usage gap towards the service quotas.

While Amazon CloudWatch already provides metrics for the FMs used in Bedrock, it might not be straightforward to calculate TPM & RPM, to aggregate token usage across application inference profiles, and see how each profile contributes to usage. Also, the quota lookup needs to be done separately via AWS service quotas. With this tool, you can specify the region and model to analyse and it will fetch the usage across last 1 hour, 1 day, 7 days, 14 days, and 30 days, each with aggregated data across the application inference profiles. It will generate HTML report containing the statistics table and time series data.

![sample report](https://raw.githubusercontent.com/awslabs/bedrock-usage-analyzer/refs/heads/main/assets/image2.png)

This tool works by calling AWS APIs from your local machine, including CloudWatch Get Metric Data and Bedrock List Inference Profiles. It then generates a JSON and HTML output file per model/system inference profile being analysed inside results folder. The tool uses metadata files in metadata folder to obtain the list of available regions and FMs and to map each FM into the AWS service quotas L code (L-xxx). You can refresh the available regions, the available foundation models, and the service quotas mapping for the FMs using the scripts in bin folder. The FM to service quotas mapping is done intelligently with the help of foundation model called through Bedrock.

**LogCost**

[LogCost](https://github.com/ubermorgenland/LogCost) is a new tool that helps you find expensive log statements by tracking and aggregating logs at the source code level. Drop-in instrumentation (just import logcost) that pinpoints which lines generate the most data, helping you cut cloud logging costs by 40-60% without guessing.

Instead of wondering where your logging costs go, LogCost shows the exact file:line, bytes logged, cost, and call count. Fix the top offenders and save hundreds monthly. Check out the README for some great examples of the output and how you can integrate this with your workloads. Really nice.

**cloudwatcher-aws-cloudformation**

[cloudwatcher-aws-cloudformation](https://github.com/cloudwatcher-dev/cloudwatcher-aws-cloudformation) is a repo that contains CloudFormation templates for monitoring AWS Organizations with CloudWatch alarms and automated email notifications. Cloudwatcher is an AWS security monitoring solution that automatically detects and alerts on suspicious activities in your AWS Organization. It monitors CloudTrail logs for security-relevant events and sends formatted email notifications when alarms are triggered.

**migration-accelerator-graviton**

[migration-accelerator-graviton](https://github.com/awslabs/migration-accelerator-graviton) is a super handy tool for those of you looking to move your workloads to AWS Graviton based instances. It will automatically analyse SBOM files and dependency manifests for Java, Node.js, Python, .NET, and Ruby applications to determine AWS Graviton (ARM64) compatibility and accelerate your migration to Graviton instances.

![architecture overview](https://raw.githubusercontent.com/awslabs/migration-accelerator-graviton/refs/heads/main/images/graviton-validator.jpg)

**ec2ssh**

[ec2ssh](https://github.com/ivoronin/ec2ssh) is a tool you might want to try out if you are not using Amazon EC2 Session Manager to connect to your EC2 instances. This tool describes itself as the Swiss Army knife for EC2 instance access. SSH, SCP, SFTP, and SSM - one tool, zero configuration. Comprehensive docs which covers everything you need to know.

**relia_oss**

[relia_oss](https://github.com/davidahmann/relia_oss) is a new project from **David Ahmann** which views itself as the "ESLint" for Cloud Costs", and the aim of this project is to help prevent cloud waste before it ships to production. Relia sits in your Pull Request. It parses your Terraform changes, estimates the monthly cost impact, and blocks the merge if you blow your budget. Check out the README for details on the workflow and how it works.

**grafq**

[grafq](https://github.com/dhth/grafq) is a project from **Dhruv Thakur** that lets you query Neo4j/AWS Neptune databases via an interactive console. The inspiration for this project came from needing a terminal based solution. In his own words

> I wrote grafq to make it easier to interact with the graph databases we use at work from the command line. I use it to quickly experiment with queries and, at times, benchmark them. It also lets me page through results or persist them to the local filesystem.

Check out the README for some nice demo screenshots and a short video of this in action. Very nicely executed tool.

**bedrock-mantle**

[bedrock-mantle](https://github.com/danilop/bedrock-mantle) is a new repo from my good friend **Danilo Poccia** that helps you explore the Amazon Bedrock OpenAI-compatible APIs from the command line. This was one of the announcements from re:Invent that perhaps slipped under everyones attention, so Danilo has put together this project and a blog post to help you explore this. Go read [Exploring the OpenAI-Compatible APIs in Amazon Bedrock: A CLI Journey Through Project Mantle](https://dev.to/aws/exploring-the-openai-compatible-apis-in-amazon-bedrock-a-cli-journey-through-project-mantle-2114) and then try this project out.

**sample-inventory-monitor-fim**

[sample-inventory-monitor-fim](https://github.com/aws-samples/sample-inventory-monitor-fim) this sample demonstrates how to use AWS Systems Manager (SSM) Inventory to monitor file changes on Amazon EC2 instances, forward findings to AWS Security Hub, and store them in Amazon Security Lake for centralised analysis and visualisation.

![solution architecture](https://raw.githubusercontent.com/aws-samples/sample-inventory-monitor-fim/refs/heads/main/res/architecture.png)

### Demos, Samples, Solutions and Workshops

**agent-sop**

[agent-sop](https://github.com/strands-agents/agent-sop) this repo provides a collection of workflows that enable AI agents to perform complex, multi-step tasks with consistency and reliability. Agent SOPs (Standard Operating Procedures) are markdown-based instruction sets that guide AI agents through sophisticated workflows using natural language, parameterised inputs, and constraint-based execution. They transform complex processes into reusable, shareable workflows that work across different AI systems and teams.

There are currently several SOPs available: code base summary, prompt driven development (pdd), code task generator, Test Driven Development code implementation, and an agentic evaluation framework.

**devtoagent**

[devtoagent](https://github.com/giolaq/devtoagent) is the first of two projects by **Giovanni Laquidara** featured in this month's edition. If you use the dev.to platform, then this project is something you should be checking out. It helps you simplify the process of creating blog posts on this platform, using agentic AI to automate some of the tasks around the initial writing, structure, illustration and publishing (in draft). As someone who uses dev.to a lot, I am going to try this out and see how it can make me more productive. Very nice work Gio.

**gio-comic**

[gio-comic](https://github.com/giolaq/gio-comic/) is a project from **Giovanni Laquidara** that will help you generate professional quality comics from natural language descriptions using Google's state-of-the-art image generation model and the Strands Agents framework. Check out the image below, which was generated using this framework.

![example image](https://media.licdn.com/dms/image/v2/D4E22AQFUL_N_Brqvkg/feedshare-shrink_2048_1536/B4EZsYwI1XGoAw-/0/1765646832333?e=1767830400&v=beta&t=_SF6JMkmEin6q2EmXyVPEXITo-LPqoH313bgYazD5RY)

**terraform-aws-secure-static-site**

[terraform-aws-secure-static-site](https://github.com/damienjburks/terraform-aws-secure-static-site) this project from **Damien Burks** was the result of some [inspired Kiro spec driven development](https://www.linkedin.com/posts/damienjburks_github-damienjburksterraform-aws-secure-static-site-activity-7404920638131306496-48YB/), that provides a secure, production ready Terraform module for hosting static websites on AWS with multi-region failover, comprehensive security hardening, and automated deployment.

Has Kiro inspired you to build something? If so, drop me a message and I would love to include it in this roundup of projects.

**sample-agentic-arcade-game-starter**

[sample-agentic-arcade-game-starter](https://github.com/aws-samples/sample-agentic-arcade-game-starter) is a fun project to check out over the holidays, providing an AI assisted game development specifications for building browser based arcade games using Kiro and Phaser 3. This repository provides complete specifications that enable Kiro to generate fully functional games from simple natural language prompts.

**sample-sonic-sip-server-js**

[sample-sonic-sip-server-js](https://github.com/aws-samples/sample-sonic-sip-server-js) provides sample code to implement an AI-powered conversation server that handles incoming phone calls using Amazon Nova Sonic in Amazon Bedrock. The server can access a customised Amazon Bedrock knowledge base for company-specific information. A flexible solution for businesses that need AI-powered phone conversation handling.

![sonic sip server architecture](https://raw.githubusercontent.com/aws-samples/sample-sonic-sip-server-js/refs/heads/main/architecture/sip-server-js.png)

### AWS and Community blog posts

**This weeks essential reading**

Here are the posts that I think are essential reads, so start here. We have more than we usually do, but thought these were all essential reads this month.

* [Cedar Joins CNCF as a Sandbox Project](https://aws.amazon.com/blogs/opensource/cedar-joins-cncf-as-a-sandbox-project/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) shares the amazing news that Cedar, an open source project that regular readers of this newsletter will know that I have a strong affinity with,  has now joined the Cloud Native Computing Foundation (CNCF) as a Sandbox project providing customers with even more reasons to check out this project to help you power your authorizations
 
* [Expanding container security and choice with Amazon ECR Public](https://aws.amazon.com/blogs/containers/expanding-container-security-and-choice-with-amazon-ecr-public/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) covers news that Amazon ECR Public, a trusted platform for container image discovery and distribution, now offers the free tier of Chainguard's security-hardened, minimalist container images to improve container security and flexibility for modern cloud-native applications [hands on]

* [Shaping the future of MCP: AWS's commitment and vision](https://aws.amazon.com/blogs/opensource/shaping-the-future-of-mcp-aws-commitment-and-vision/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) looks at how with MCP now under the neutral governance of the Linux Foundation, this will enable the long term success and widespread development of the protocol that has become a standard component of agentic architectures

**Community**

Each month I spend time reading posts from across the AWS community on open source topics. In this section I share what personally caught my eye and interest, and I hope that many of you will also find them interesting. 

Starting strongly this month with **James Ward's** post [MCP Elicitations with Java & Spring AI](https://builder.aws.com/content/36lU1MoMHb7tgVSbS3WTX5t6s31/mcp-elicitations-with-java-and-spring-ai?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) which shows you how to use the new Elicitations feature of the Model Context Protocol (MCP) spec that allows you to introduce interactivity to your MCP interactions, providing some demo code using Spring AI. Very nice. Sticking with Java for the time being, in the post  [Guide: Integrating AWS APerf & async-profiler with Java Applications (Host & Container)](https://builder.aws.com/content/36NF5RGI77GwiQsxrocL1KBi0JD/guide-integrating-aws-aperf-and-async-profiler-with-java-applications-host-and-container?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) **Ziv Klempner** explains how to set up and use a couple of nice open source projects, AWS APerf and async-profiler, for profiling Java applications. Sticking with the optimisation theme, **Brian O'Keefe** shows how you can leverage Strands Agent agentic AI framework to provide an agent with an openCypher query to identify optimisations in this post [Query Tuner Agent](https://builder.aws.com/content/36LO6raooq19LNxlAilLGhmIQ6O/query-tuner-agent?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el).

AWS Community Builder **Ajaykumar K V** showed you how you can use Amazon Bedrock's Nova models, together with Strands Agents framework, and Mem0's for the memory layer,  to create an AI assistant that maintains context across conversations, learns user preferences, and provides genuinely personalised interactions. [Building a Memory-Powered AI Agent: A Journey with Amazon Bedrock, Strands, and Mem0](https://builder.aws.com/content/35INnEyn81OR4bDwujsvfkSUDzt/building-a-memory-powered-ai-agent-a-journey-with-amazon-bedrock-strands-and-mem0?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) is a nice post, so go check it out. 

If you wanted to know how you might implement feature flags in your AWS CDK stacks, then AWS Community Builder **kazuho cryer-shinozuka** has you covered in his post, [Implementing Feature Flags in AWS CDK: A Contributor's Guide](https://dev.to/aws-builders/implementing-feature-flags-in-aws-cdk-a-contributors-guide-fdf). Sticking within the realms of DevOps, we have AWS Community Builder **Chinmay Tonape** who shared [GitOps with ArgoCD on Amazon EKS using Terraform: A Complete Implementation Guide](https://dev.to/aws-builders/gitops-with-argocd-on-amazon-eks-using-terraform-a-complete-implementation-guide-1inc) which walks you through building a complete production grade GitOps workflow using ArgoCD on Amazon EKS. To close this round up, and featuring one of my favourite open source technologies Firecracker, AWS Community Builder **Matt Bacchi** provides you with a great introduction and overview of what Firecracker is. If you like what you read, Matt is planning more content on Firecracker so be sure to keep an eye out for that.

Thats all for this month and 2025 - I have really enjoyed the community source content so please keep it up. If you have an open source article you want to share with the community, drop me a message (LinkedIn, or via [ricsue@amazon.co.uk](mailto:ricsue@amazon.co.uk) and I will be sure to check it out.

**GenAI**

* [Customize agent workflows with advanced orchestration techniques using Strands Agents](https://aws.amazon.com/blogs/machine-learning/customize-agent-workflows-with-advanced-orchestration-techniques-using-strands-agents/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - takes a look at how to use Strands Agents, an open source SDK, to implement advanced orchestration techniques for customising agent workflows and building reliable, transparent, and maintainable AI systems [hands on]

![agentic ai swimlane interactions](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2025/11/25/agent_orchestration.jpg)

**Cloud Native**

* [Maximizing the Value of Red Hat OpenShift on AWS](https://aws.amazon.com/blogs/ibm-redhat/maximizing-the-value-of-red-hat-openshift-on-aws/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - first provides a technical overview of Red Hat OpenShift Service on AWS (ROSA), a turnkey platform for building and managing containerised applications, before exploring strategies for optimising ROSA subscription fees and AWS infrastructure costs

* [Prometheus MCP Server: AI-Driven Monitoring Intelligence for AWS Users](https://aws.amazon.com/blogs/mt/prometheus-mcp-server-ai-driven-monitoring-intelligence-for-aws-users/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - walks you through the open source Prometheus Model Context Protocol (MCP) server that enables AI code assistants to interact with Prometheus monitoring infrastructure through natural language queries [hands on]

**Data and Analytics**

* [Introducing AWS Glue 5.1 for Apache Spark](https://aws.amazon.com/blogs/big-data/introducing-aws-glue-5-1-for-apache-spark/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - looks at the new features and upgrades in AWS Glue 5.1, including the upgrade to Apache Spark 3.5.6, support for newer open table format libraries, and new Apache Iceberg features like materialised views and format version 3.0 [hands on]
* [Introducing the Apache Spark troubleshooting agent for Amazon EMR and AWS Glue](https://aws.amazon.com/blogs/big-data/introducing-the-apache-spark-troubleshooting-agent-for-amazon-emr-and-aws-glue/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - dives into the newly launched Apache Spark troubleshooting agent that can eliminate hours of manual investigation for data engineers and scientists working with Amazon EMR or AWS Glue by automatically analysing workloads and delivering actionable recommendations [hands on]

![overview of the apache spark troubleshooting agent](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2025/12/16/BDB-5690-1.jpg)

* [Introducing Apache Spark upgrade agent for Amazon EMR](https://aws.amazon.com/blogs/big-data/introducing-apache-spark-upgrade-agent-for-amazon-emr/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - introduces an AI powered Apache Spark upgrade agent for Amazon EMR that automates the process of upgrading Spark versions, handling code analysis, fixes, and validation to reduce the time and effort required for version upgrades from months to hours [hands on]

![overview of apache spark upgrade agent](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2025/12/15/BDB-5681-1.png)

* [Accelerate Apache Hive read and write on Amazon EMR using enhanced S3A ](https://aws.amazon.com/blogs/big-data/accelerate-apache-hive-read-and-write-on-amazon-emr-using-enhanced-s3a/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el)- walks you through how to accelerate Apache Hive read and write performance on Amazon EMR using the enhanced S3A file system, which offers faster queries, tuned defaults, and integration with AWS services [hands on]

* [Building an open warehouse architecture: Supabase's‚ integration with Amazon S3 Tables](https://aws.amazon.com/blogs/storage/building-an-open-warehouse-architecture-supabases-integration-with-amazon-s3-tables/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - explores how Supabase, an open-source Postgres development platform, addresses the challenge of scaling analytics by combining Postgres for transactional operations and Amazon S3 Tables for analytical workloads

* [Introducing Apache Iceberg materialized views in AWS Glue Data Catalog](https://aws.amazon.com/blogs/big-data/introducing-apache-iceberg-materialized-views-in-aws-glue-data-catalog/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - shows how the AWS Glue Data Catalog now supports Apache Iceberg materialised views, which simplify data pipelines and accelerate data lake query performance by storing pre-computed results of queries in Iceberg format and automatically updating them as the underlying data changes [hands on]

**Other posts to check out**

* [Optimize WordPress performance on Amazon EKS with Amazon FSx for OpenZFS](https://aws.amazon.com/blogs/storage/optimize-wordpress-performance-on-amazon-eks-with-amazon-fsx-for-openzfs/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - shows you how to optimise WordPress performance on Amazon EKS using Amazon FSx for OpenZFS, which provides high-throughput, low-latency storage for stateful containerised applications and integrates with the CSI driver to streamline persistent storage [hands on]

![Wordpress cloud native architecture with OpenZFS](https://d2908q01vomqb2.cloudfront.net/e1822db470e60d090affd0956d743cb0e7cdf113/2025/11/17/stg1684-image-1.png)

* [Modernize ASP.NET MVC Razor UI with AWS Transform](https://aws.amazon.com/blogs/dotnet/modernize-asp-net-mvc-razor-ui-with-aws-transform/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - Describes how AWS Transform can modernise ASP.NET MVC Razor UI applications by porting them to ASP.NET Core, reducing operating costs and enabling cross platform deployment [hands on]

* [AWS SDK for JavaScript aligns with Node.js release schedule](https://aws.amazon.com/blogs/developer/aws-sdk-for-javascript-aligns-with-node-js-release-schedule/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - looks at how the AWS SDK for JavaScript v3 is aligning with the Node.js release schedule, including end of support for specific Node.js and ECMAScript versions, and the benefits of upgrading to newer Node.js versions [hands on]

* [Simplify IAM policy creation with IAM Policy Autopilot, a new open source MCP server for builders](https://aws.amazon.com/blogs/aws/simplify-iam-policy-creation-with-iam-policy-autopilot-a-new-open-source-mcp-server-for-builders/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - covers one of my favourite announcements from re:Invent, and looks at an open source tool called IAM Policy Autopilot that analyses application code and generates valid AWS Identity and Access Management (IAM) policies to help builders accelerate initial development and focus on building applications [hands on]

* [Introducing the AWS Infrastructure as Code MCP Server: AI-Powered CDK and CloudFormation Assistance](https://aws.amazon.com/blogs/devops/introducing-the-aws-infrastructure-as-code-mcp-server-ai-powered-cdk-and-cloudformation-assistance/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) - takes a look at another MCP Server, this time one that assists with searching AWS CloudFormation and Cloud Development Kit (CDK) documentation, validating templates, and troubleshooting deployments [hands on]

### Quick updates

**Strands Agents**

In May, we open sourced the Strands Agents SDK, an open source python framework that takes a model-driven approach to building and running AI agents in just a few lines of code. Today, we’re announcing that TypeScript support is available in preview. During re:Invent, one of the big announcements was that developers can now choose between Python and TypeScript for building Strands Agents.

TypeScript support in Strands has been designed to provide an idiomatic TypeScript experience with full type safety, async/await support, and modern JavaScript/TypeScript patterns. Strands can be easily run in client applications, in browsers, and server-side applications in runtimes like AWS Lambda and Bedrock AgentCore. Developers can also build their entire stack in Typescript using the AWS CDK.

We’re also announcing three additional updates for the Strands SDK. First, edge device support for Strands Agents is generally available, extending the SDK with bidirectional streaming and additional local model providers like llama.cpp that let you run agents on small-scale devices using local models. Second, Strands steering is now available as an experimental feature, giving developers a modular prompting mechanism that provides feedback to the agent at the right moment in its lifecycle, steering agents toward a desired outcome without rigid workflows. Finally, Strands evaluations is available in preview. Evaluations gives developers the ability to systematically validate agent behaviour, measure improvements, and deploy with confidence during development cycles.

**MLflow**

Amazon SageMaker AI now offers a serverless MLflow capability that dynamically scales to support AI model development tasks. With MLflow, AI developers can begin tracking, comparing, and evaluating experiments without waiting for infrastructure setup. As customers across industries accelerate AI development, they require capabilities to track experiments, observe behaviour, and evaluate the performance of AI models, applications and agents. However, managing MLflow infrastructure requires administrators to continuously maintain and scale tracking servers, make complex capacity planning decisions, and deploy separate instances for data isolation. This infrastructure burden diverts resources away from core AI development and creates bottlenecks that impact team productivity and cost effectiveness.

With this update, MLflow now scales dynamically to deliver fast performance for demanding and unpredictable model development tasks, then scales down during idle time. Administrators can also enhance productivity by setting up cross-account access via Resource Access Manager (RAM) to simplify collaboration across organisational boundaries. The serverless MLflow capability on Amazon SageMaker AI is offered at no additional charge and works natively with familiar Amazon SageMaker AI model development capabilities like SageMaker AI JumpStart, SageMaker Model Registry and SageMaker Pipelines. Customers can access the latest version of MLflow on Amazon SageMaker AI with automatic version updates.

**Apache Iceberg**

Amazon S3 Tables now support automatic replication of Apache Iceberg tables across AWS Regions and accounts. This new capability replicates your complete table structure, including all snapshots and metadata to reduce query latency and improve data accessibility for global analytics workloads. S3 Tables replication automatically creates read-only replica tables in your destination table buckets, backfills them with the latest state of the source table, and continuously monitors for new updates to keep replicas in sync. Replica tables can be configured with independent snapshot retention policies and encryption keys from source tables to meet compliance and data protection requirements. You can query replica tables using Amazon SageMaker Unified Studio or any Iceberg-compatible engine including Amazon Athena, Amazon Redshift, Apache Spark, and DuckDB.

**Apache Spark**

AWS announces the Apache Spark upgrade agent, a new capability that accelerates Apache Spark version upgrades for Amazon EMR on EC2 and EMR Serverless. The agent converts complex upgrade processes that typically take months into projects spanning weeks through automated code analysis and transformation. Organisations invest substantial engineering resources analysing API changes, resolving conflicts, and validating applications during Spark upgrades. The agent introduces conversational interfaces where engineers express upgrade requirements in natural language, while maintaining full control over code modifications.

The Apache Spark upgrade agent automatically identifies API changes and behavioural modifications across PySpark and Scala applications. Engineers can initiate upgrades directly from SageMaker Unified Studio, Kiro CLI or IDE of their choice with the help of MCP (Model Context Protocol) compatibility. During the upgrade process, the agent analyses existing code and suggests specific changes, and engineers can review and approve before implementation. The agent validates functional correctness through data quality validations. The agent currently supports upgrades from Spark 2.4 to 3.5 and maintains data processing accuracy throughout the upgrade process.

**PostgreSQL**

Amazon Aurora PostgreSQL-Compatible Edition now supports PostgreSQL version 18.1 in the Amazon RDS Database Preview Environment, allowing you to evaluate PostgreSQL 18.1 on Amazon Aurora PostgreSQL. PostgreSQL 18.1 was released by the PostgreSQL community on September 9, 2025.  PostgreSQL 18.1 includes "skip scan" support for multicolumn B-tree indexes and improves WHERE clause handling for OR and IN conditions. It introduces parallel GIN index builds and updates join operations. Observability improvements show buffer usage counts and index lookups during query execution, along with a per-connection I/O utilisation metric.

**Kubernetes**

There were a few great updates for cloud native folks in December.

Amazon Elastic Kubernetes Service (EKS) announced the general availability of EKS Capabilities, a fully-managed extensible set of Kubernetes-native platform features for workload deployment, AWS cloud resource management, and Kubernetes resource composition and orchestration. EKS Capabilities provides out-of-the-box platform features and offloads operations to AWS, improving the performance and security of your platform components. EKS Capabilities streamlines building and scaling with Kubernetes, allowing you to focus on deploying applications rather than maintaining platform infrastructure. These capabilities run in AWS-owned infrastructure separate from your clusters, with AWS handling auto scaling, patching, and upgrading. Application developers get ready-to-use platform capabilities that enable faster workload deployment and scaling across the organisation, while platform teams can offload operational tasks to AWS. Three capabilities are available at launch including continuous deployment with Argo CD, AWS resource management through AWS Controllers for Kubernetes (ACK), and dynamic resource orchestration using Kube Resource Orchestrator (KRO).

Check out the announcement post, [Announcing Amazon EKS Capabilities for workload orchestration and cloud resource management](https://aws.amazon.com/blogs/aws/announcing-amazon-eks-capabilities-for-workload-orchestration-and-cloud-resource-management/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) to dive deeper into this launch.

Following that was news of the enhanced network policy capabilities in Amazon EKS, allowing customers to improve the network security posture for their Kubernetes workloads and their integrations with cluster-external destinations. This enhancement builds on network segmentation features previously supported in EKS. Now you can centrally enforce network access filters across the entire cluster, as well as leverage Domain Name System (DNS) based policies to secure egress traffic from your cluster’s environment. As customers continue to scale their application environments using EKS, network traffic isolation is increasingly fundamental for preventing unauthorised access to resources inside and outside the cluster. To address this, EKS introduced support for Kubernetes NetworkPolicies in the Amazon VPC Container Network Interface (VPC CNI) plugin, allowing you to segment pod-to-pod communication at a namespace level. Now you can further strengthen the defensive posture for your Kubernetes network environment by centrally managing network filters for the whole cluster. Also, cluster admins now have a more stable and predictable approach for preventing unauthorised access to cluster-external resources in the cloud or on-premesis using egress rules that filter traffic to external endpoints based on their Fully Qualified Domain Name (FQDN).

If this is more up your street, then dive into [Amazon EKS introduces enhanced network policy capabilities](https://aws.amazon.com/blogs/containers/amazon-eks-introduces-enhanced-network-policy-capabilities/?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) for the low down.

**Qiskit**

Amazon Braket now supports Qiskit 2.0, enabling quantum developers to use the latest version of the most popular quantum software framework with native primitives and client-side compilation capabilities. With this release, Braket provides native implementations of Qiskit's Sampler and Estimator primitives that leverage Braket's program sets for optimised batching, reducing execution time and costs compared to generic wrapper approaches. The native primitives handle parameter sweeps and observable measurements service-side, eliminating the need for customers to implement this logic manually. Additionally, the bidirectional circuit conversion capability enables customers to use Qiskit's extensive compilation framework for client-side transpilation before submitting to Braket devices, providing the control and reproducibility that enterprise users and researchers require for device characterisation experiments and custom compilation passes.

**Amazon Linux 2023**

AWS Elastic Beanstalk is a service that provides the ability to deploy and manage applications in AWS without worrying about the infrastructure that runs those applications. 

AWS Elastic Beanstalk now enables customers to build and deploy Python 3.14 applications on Amazon Linux 2023 (AL2023) platform. This latest platform support allows developers to leverage the newest features and improvements in Python while taking advantage of the enhanced security and performance of AL2023. Python 3.14 on AL2023 delivers enhanced interactive interpreter capabilities, improved error messages, important security and API improvements. Developers can create Elastic Beanstalk environments running Python 3.14 on AL2023 through the Elastic Beanstalk Console, CLI, or API.

In more news, AWS Elastic Beanstalk now also enables customers to build and deploy Node.js 24 applications on Amazon Linux 2023 (AL2023) platform. This latest platform support allows developers to leverage the newest features and improvements in Node.js while taking advantage of the enhanced security and performance of AL2023. Node.js 24 on AL2023 delivers updates to the V8 JavaScript engine, npm 11, and security and performance improvements. Developers can create Elastic Beanstalk environments running Node.js 24 on AL2023 through the Elastic Beanstalk Console, CLI, or API.

### Videos of the month

This month the videos are all from re:Invent, from across the open source track and beyond. These are only the ones that I have had a chance to look at, I still have a backlog which I will be checking out over the coming weeks.

**kro: Simplifying Kubernetes Resource Orchestration (OPN308)**

In this video, **Shani Adadi Kazaz** and **Petro Kashlikov** introduce kro, the open source tool revolutionising Kubernetes resource management through configuration-based orchestration. This vendor-neutral solution eliminates custom coding needs through Simple Schema and CEL expressions, making complex resource dependencies manageable for teams of all sizes. The demonstration shows how kro transforms Kubernetes into a centralised platform that accelerates developer velocity, improves fleet management and streamlines infrastructure deployment while maintaining organisational best practices and governance.

{{< youtube 95xCRSsevaY >}}

**Building agentic AI platform engineering solutions with open source (OPN303)**

**Hasith Kalpage** and **Niall Thomson** shared their vision on driving innovation through open source agentic AI, and enhancing work-life quality for platform engineers worldwide. In the session they explored real-world examples of how platform teams can apply autonomous agentic AI to their organisations, integrating AWS services alongside other open source projects such as Kubernetes, ArgoCD, Backstage and more.

{{< youtube xwzInf90iUc >}}

**Better, faster, cheaper: How Valkey is revolutionizing caching (DAT458)**

In this video, **Madylon Olson** and **Joseph Idzoriek** share how open source Valkey and Amazon ElastiCache is transforming distributed caching. They look at innovations including probabilistic data structures like bloom filters, a memory-efficient dictionary reducing usage by up to 40%, and multi-threaded architecture enabling 230% instantaneous scaling. You will learn about the infrastructure that allows ElastiCache to seamlessly patch hundreds of thousands of customers while maintaining high availability, even during extreme workloads like Prime Day's trillion requests per minute.

{{< youtube iUw1d4bUNJk >}}

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes:  Madylon Olson, Joseph Idzoriek, Hasith Kalpage, Niall Thomson, Shani Adadi Kazaz, Petro Kashlikov, Aaron Dailey, Abhi Karode, Ameen Khan, Andrew (Qingjie) Ren, Andrew Kim, Anmol Sundaram, Arunav Gupta, Baishali Chaudhury, Bo Li, Channy Yun (윤석찬), Chiho Sugimoto, David Pallmann, Fabien Gaud, Gaurav Gundal, Giovanni Matteo Fumarola, Himanshu Mishra, Idriss Laouali Abdou, Isaac Privitera, Jake Zych, James Ward, Jeremy Samuel, Kartik Panjabi, Keerthi Chadalavada, Kiro, Lara Langdon, Layth Yassin, Leon Lin, Liz Duke, Lukonde Mwila, Maheedhar Reddy Chappidi, Mahesh Mishra, Malinda Malwala, McCall Peltier, Meg Sarros, Micah Walter, Miraj Ranpura, Mohamed Sherif, Mohit Saxena, Muhammad Ali Gulzar, Mukul Prasad, Munish Dabra, Nick Aldridge, Noritaka Sekiyama, Paramvir Singh, Peter Manastyrny, Peter Tsai, Pradeep Patel, Pritesh Patel, Rahul Ghosh, Raj Jain, Raja SP, Rajendra Gujja, Ramesh Kandasamy, Riccardo Busetti, Shubham Mehta, Siddhesh Jog, Sourav Kundu, Steve Mirman, Tomohiro Tanaka, Tristan Poisson, Trivikram Kamat, Vaibhav Naik, Vidyashankar Sivakumar, Vishal Kajjam, Wei Tang, Will Matos, and XiaoRun Yu.

### Merry Christmas and Happy Holidays

Wishing you all a fantastic time over the festive period, and look forward to coming back in 2026.

Made with ♥ from DevRel