---
title: 'AWS open source newsletter #218'
date: '2026-01-28'
tags : [ oss-newsletter, aws open source, AWS CDK, AWS Amplify, Valkey, Strands Agents, FreeBSD, vault, Istio, Kiali, Kubernetes, AWS Lambda Powertools, DuckDB, Spring, Langraph, MLflow, AWS IoT Greengrass, GitLab, ArgoCD, kro, Apache Airflow, Apache Iceberg, dbt, OpenSearch, PostgreSQL,  Apache Kafka, Mountpoint for Amazon S3, Karpenter, OpenShift, Apache Spark, Gradle, RabbitMQ, Amazon Corretto, MySQL, AWS Neuron SDK, Ubuntu, InfluxDB]
canonicalUrl: "https://dev.to/aws/aws-open-source-newsletter-218-3e3m"
---


##  Edition #218 - January 2026

Welcome to issue #218 of the AWS open source newsletter, the newsletter where I try and provide you the best open source on AWS content.  Many of you will be on your way to FOSDEM, and sadly I will not be there this year - although I will be in spirit as my weekend will be spent watching the [livestreams](https://fosdem.org/2026/schedule/day/saturday/).

In this months edition we have a nice selection of projects - from tools to help you review and audit your cloud resources, to projects that simplify deployment of complete AI stacks, and cool terminal based tools that will delight a lot of you I am sure. The projects will keep you busy until next month for sure, but we also have plenty of reading material in this months newsletter. In this edition we have featured projects that include AWS CDK, AWS Amplify, Valkey, Strands Agents, FreeBSD, vault, Istio, Kiali, Kubernetes, AWS Lambda Powertools, DuckDB, Spring, Langraph, MLflow, AWS IoT Greengrass, GitLab, ArgoCD, kro, Apache Airflow, Apache Iceberg, dbt, OpenSearch, PostgreSQL,  Apache Kafka, Mountpoint for Amazon S3, Karpenter, OpenShift, Apache Spark, Gradle, RabbitMQ, Amazon Corretto, MySQL, AWS Neuron SDK, Ubuntu, InfluxDB. Phew, that should keep you all very busy!

Check out the list of contributors at the end of the newsletter, and as always, get in touch if you want me to feature your projects in this open source newsletter. 

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution. The projects mentioned here do not represent any formal recommendation or endorsement, I am just sharing for greater awareness as I think they look useful and interesting!*

### Tools

**CloudSlash**

[CloudSlash](https://github.com/DrSkyle/CloudSlash) CloudSlash is a local-first AWS forensic engine that automatically identifies and safely remediates cloud waste through dependency graph analysis and mathematical optimisation. Unlike passive monitoring tools, it actively finds unused resources, calculates optimal configurations using linear programming, and provides safe cleanup with rollback capabilities through its "Lazarus Protocol." The tool combines Git/Terraform provenance tracking with sophisticated algorithms to deliver 15-25% cost reductions while maintaining zero-trust security principles.

Make sure you check out the README that goes into a lot of detail on the specifics. Well worth reading.

![demo screen of cloudslash](https://raw.githubusercontent.com/DrSkyle/CloudSlash/refs/heads/main/assets/cloudslashdetailview.png)

**CleanCloud**

[CleanCloud](https://github.com/cleancloud-io/cleancloud) is a cloud hygiene tool that helps SRE teams identify cost draining orphaned and inactive resources across their AWS environments without any risk of accidental deletion. Unlike automated cleanup tools, it operates in strictly read-only mode using only safe API operations, making it perfect for regulated environments where security approval is critical. The tool provides visibility into cloud waste through configurable scans and audit-friendly reporting, enabling teams to optimise costs through informed decision-making rather than risky automation. Make sure you dive into the README which provides a lot of detail on what you can do with this tool.

**AWS WasteFinder**

[AWS WasteFinder](https://github.com/devopsjunctionn/AWS-WasteFinder) is a Python CLI tool that helps you reign in your AWS bills by automatically scanning all regions for unused and underutilised resources. It identifies seven types of wasteful resources, from unattached EBS volumes to idle load balancers, and calculates exactly how much money you're wasting monthly and yearly. The tool takes a safety first approach by being completely read-only and generating AWS CLI commands for you to review before taking any action.

**sample-capacity-finder-for-ec2-capacity-block-and-sagemaker-training-plan**

[sample-capacity-finder-for-ec2-capacity-block-and-sagemaker-training-plan](https://github.com/aws-samples/sample-capacity-finder-for-ec2-capacity-block-and-sagemaker-training-plan) is a neat tool (streamlit app) that makes it easy to explore available AWS EC2 Capacity Blocks and SageMaker Training Plans across regions and instance types. 

![demo of capacity finder tool](https://raw.githubusercontent.com/aws-samples/sample-capacity-finder-for-ec2-capacity-block-and-sagemaker-training-plan/refs/heads/main/assets/app-screenshot.png)

**LEAP Stacks**

[LEAP Stacks](https://github.com/bfateen/leapstacks2) simplifies deploying AI applications on AWS by providing prebuilt CloudFormation templates that get production ready chatbots, RAG systems, and AI agents running in minutes. This allows developers to focus on their AI logic while the platform handles deployment, monitoring, and cost controls automatically. It bridges the notorious "Production Valley of Despair" where AI prototypes fail to scale by delivering complete, observable systems rather than just code snippets or local demos. This repo represents v2 of this project, and having spent some time with it, it is defo one to check out folks - great work **Basil Fateen**.

**s3sh**

[s3sh](https://github.com/dacort/s3sh) is another great project from regular open source contributor **Damon Cortesi**. s3sh transforms S3 bucket exploration by providing a familiar Unix-like shell interface for cloud storage navigation. Built in Rust, it allows developers to use standard commands like `ls`, `cd`, and `cat` to browse S3-compatible storage systems as if they were local filesystems. The tool's killer feature is the ability to `cd` directly into compressed archives and parquet files stored in S3 without downloading them, using efficient range requests for streaming access. This makes it invaluable for data engineers, DevOps teams, and anyone who prefers command-line interfaces over web consoles for S3 exploration.

**pathfinding.cloud**

[pathfinding.cloud](pathfinding.cloud) is a comprehensive, community-maintained library create by **AWS Community Builder Seth Art** that documents AWS IAM privilege escalation paths. This project builds upon foundational research by Spencer Gietzen at Rhino Security Labs and subsequent contributions from many other security researchers. The website provides detailed documentation of each privilege escalation path - go check out the README to get a glimpse. (Hat tip to **AWS Community Builder Nick Jones** for making me aware of this project).

**AWS-Brief**

[AWS-Brief](https://github.com/mhmtayberk/aws-brief)  is an AI powered automation tool from **AWS Community Builder Mehmet Ayberk** that solves the information overload problem for cloud teams by intelligently monitoring 36+ official AWS RSS feeds and filtering out noise to deliver only relevant updates. It uses AI models to analyse AWS announcements, security bulletins, and service updates, then sends curated summaries and real-time alerts through your preferred communication channels. Instead of manually sifting through hundreds of AWS updates weekly, developers and DevOps teams get actionable intelligence with impact assessments delivered directly to Slack, Teams, Discord, or email. This ensures teams stay current with critical AWS developments without drowning in irrelevant notifications. Check out the README, but lots of deployment options (including local models if you use Ollama).

**stakpak**

[stakpak](https://github.com/stakpak/agent) is an open source DevOps agent from **AWS Community Builder Noureldin Ehab** that helps teams ship faster by helping them secure, deploy, and maintain production infrastructure from their terminal. Works with any LLM (Claude, GPT, Gemini), handles secrets securely, and uses customisable rulebooks to guide operational workflows from generating Terraform and Kubernetes configs to dockerizing apps and troubleshooting CI/CD. Check out the README and the [docs](https://stakpak.gitbook.io/docs) to help you get started.

![demo of stakpak](https://raw.githubusercontent.com/stakpak/agent/refs/heads/main/assets/stakpak-overview.gif)

**git-kiro-powers**

[kiro-powers](https://github.com/srobroek/kiro-powers) This project appears to be an experimental repository that provides some sample Kiro Git Powers.  The description of the Power says "Complete guide for Git version control with workflows, conventional commits, pre-commit hooks, and best practices for professional development". From the repo, check out the .git directory which reveals the POWER.md and support assets.

**AWS Amplify Gen 2 Kiro Power**

[AWS Amplify Gen 2 Kiro Power](https://github.com/davide-desio-eleva/amplify-gen2-kiro-power) provides a Kiro POWER that provides a starter template for creating applications using React+Vite and AWS Amplify, with a focus on easy setup for authentication, API, AI, and database capabilities.

This template equips you with a foundational React application integrated with AWS Amplify, optimized for scalability and performance. It is perfect for developers aiming to kickstart their projects with pre-configured AWS services like Cognito, AppSync, Bedrock, and DynamoDB.

**taws**

[taws](https://github.com/huseyinbabal/taws) taws is a cool project from **Hüseyin Babal** that provides a terminal based interface for managing AWS resources, that is built in Rust for speed and reliability. It transforms the AWS Console experience into a keyboard-driven terminal application, allowing developers and DevOps engineers to browse, monitor, and manage their entire AWS infrastructure without leaving the command line. With support for 94+ resource types across 60+ AWS services, it provides a unified dashboard that eliminates the need to constantly switch between the web console and CLI tools. 

![demo screen of taws](https://raw.githubusercontent.com/huseyinbabal/taws/refs/heads/master/assets/screenshot-ec2.png)

**run-mcp**

[run-mcp](https://github.com/serverless-dna/run-mcp) comes from the fair hands of **AWS Hero Michael Walmsley** and provides a security focused wrapper that solves a critical vulnerability in MCP (Model Context Protocol) servers by running them in isolated containers instead of with full user permissions. It's a drop-in replacement that requires only changing `uvx` or `npx` to `run-mcp` in your configuration, instantly sandboxing third-party MCP servers from sensitive data like SSH keys and AWS credentials. The tool abstracts away container complexity while providing explicit permission controls, making it safe to run untrusted MCP servers with AI assistants like Kiro and others. Check out his supporting blog post, [Run Any MCP Server Securely Without Changing Its Config](https://serverlessdna.com/strands/projects/introducing-run-mcp).

**dynamo-lens**

[dynamo-lens](https://github.com/rasjonell/dynamo-lens) is a project from **Gurgen** that provides you with a desktop companion for Amazon DynamoDB built with Go + Wails. You can use it to explore tables, inspect and mutate items, and manage multiple environments from a single native app.

**pydynox**

[pydynox](https://github.com/leandrodamascena/pydynox) is a high performance DynamoDB ORM for Python that combines the simplicity of Python with the speed of Rust for database operations. It provides a class based interface similar to PynamoDB but delivers significantly faster serialisation and batch processing through its Rust core. Developers get comprehensive DynamoDB functionality including transactions, queries, and advanced features like encryption and compression, all wrapped in a modern Python API. It's designed for teams building AWS applications who need both developer productivity and enterprise-grade performance.

The repo also includes a .ai directory that provides guidance if you are using AI coding assistants (or want to use them) to contribute to this project. I am increasingly seeing this appear in the repos that I explore.

**Fast CloudFormation Validation for VS Code**

[WA2 VS Code Extension](https://github.com/unremarkable-technology/wa2-vscode-extension) WA2 is a high-performance VS Code extension that provides lightning-fast CloudFormation template validation, built with Rust and designed to be 9× faster than existing tools. It validates AWS CloudFormation templates in real-time, checking syntax, structure, and resource properties against official AWS schemas to catch errors early in development. The extension supports 1000+ AWS resource types and all intrinsic functions, delivering sub-second validation with precise error locations. For DevOps engineers and cloud architects working with Infrastructure as Code, WA2 offers a modern, performance focused alternative to slow existing validation tools. Very cool indeed.

**AWS Loggy**

[AWS Loggy](https://github.com/aegixx/aws-loggy) is a fast native desktop application that transforms how developers interact with AWS CloudWatch logs. Instead of wrestling with the slow, browser-based AWS Console, developers get a responsive desktop app with real-time log streaming, advanced filtering, and virtualised rendering that can handle 50,000+ log entries without breaking a sweat. Built with Tauri and TypeScript, it provides the performance of a native app with modern web UI capabilities, making CloudWatch log analysis actually enjoyable.

![demo screenshot of aws loggy](https://raw.githubusercontent.com/aegixx/aws-loggy/refs/heads/main/media/screenshot.png)

**cloudfront_log_parser**

[cloudfront_log_parser](https://github.com/headforthecloud/cloudfront_log_parser) is a new project from **AWS Community Builder Simon Hanmer** that is perfect for those of you running Hugo static sites on Amazon S3.  Using Kiro CLI to build this tool, cloudfront_log_parser helps you extract your site analytics (and other useful KPIs) from the CloudFront logs. Checkout the REAMDE to see how to configure and run this to get the insights you want.

**AWS Serverless Webhooks**

[AWS Serverless Webhooks](https://github.com/boringContributor/aws-serverless-webhooks) is a self-hosted, production-ready webhook-as-a-service platform that runs entirely on your AWS infrastructure using CDK. It eliminates vendor lock-in while providing reliable webhook delivery through AWS Durable Functions with automatic retries and comprehensive tracking. Developers can integrate it seamlessly with existing EventBridge events and manage everything through both programmatic APIs and a visual React interface. It's essentially your own [Svix](https://www.svix.com/) alternative that leverages serverless technologies on AWS.

**Instancepedia**

[Instancepedia](https://github.com/pfrederiksen/instancepedia) Instancepedia is a Python powered EC2 instance browser that brings AWS's instance types directly to your terminal. It provides both an interactive TUI for exploration and a scriptable CLI for automation, delivering realtime pricing across all AWS models (on-demand, spot, reserved, savings plans) with advanced filtering and comparison capabilities. Developers and DevOps engineers can quickly find the optimal instance type for their workloads while analysing cost implications and performance trade-offs. The tool uses only free AWS APIs, making it a zero-cost solution for infrastructure decision-making.

![example screenshot of instancepedia](https://raw.githubusercontent.com/pfrederiksen/instancepedia/main/screenshots/screenshot-instance-list.png)

**cdk-terrain**

[cdk-terrain](https://github.com/open-constructs/cdk-terrain) is a community fork of the Cloud Development Kit for Terraform (CDKTF). CDKTF/CDKTN allows you to use familiar programming languages to define cloud infrastructure and provision it through HashiCorp Terraform or OpenTofu. This gives you access to the entire Terraform/OpenTofu ecosystem without learning HashiCorp Configuration Language (HCL) and lets you leverage the power of your existing toolchain for testing, dependency management, etc.

The project currently support TypeScript, Python and Go, as is a work in progress. If you were using cdktf before, then you probably want to check this out.

**BetterDB for Valkey**

[BetterDB for Valkey](https://github.com/betterdb-inc/vscode) provides a nice VSCode extension for those of you working with Valkey. Check out the README for the current capabilities. The project is looking for contributions/collaborations, so if you love Valkey and use VSCode, why not give this a look.

![screenshot of editing Valkey values in VSCode](https://raw.githubusercontent.com/BetterDB-inc/vscode/refs/heads/master/resources/screenshots/editor.png)

### Demos, Samples, Solutions and Workshops

**strands-agent-template**

[strands-agent-template](https://github.com/deeheber/strands-agent-template) is a starter project from **AWS Hero Danielle Heberling** that will provide you with everything you need to get started with Strands Agents on Amazon Bedrock AgentCore. To help you get started he has helpfully put together a blog post, [A Strands Agent Template (For the Impatient)](https://dev.to/aws-heroes/a-strands-agent-template-for-the-impatient-412j)

**AWS Generative AI Solution Box**

[AWS Generative AI Solution Box](https://github.com/aws-samples/sample-one-click-generative-ai-solutions) This project eliminates the complexity of deploying generative AI applications by providing one-click CloudFormation templates for popular open source AI tools on AWS. Some of you will need to use translate tools to read the README, but you can also head to the deployments directory where you will see the list of cool projects that you can easily deploy with just a few clicks.

The one that I was most interested in is running Kiro IDE on a cloud based desktop over DCV, but others include ComfyUI, Langfuse, dify, and more.

**Image Downscaler and WebP Converter**

[Image Downscaler and WebP Converter](https://github.com/allenheltondev/image-downscaler) provides a serverless AWS solution that automatically optimises images for web delivery by converting them to WebP format and generating multiple responsive sizes. When you upload an image to S3, it triggers a Rust-powered Lambda function that creates optimised versions (240px to 1920px) and serves them globally through CloudFront CDN. It intelligently serves WebP to compatible browsers while falling back to original formats for older browsers, eliminating the need to manually manage image optimisation pipelines. Perfect for developers who want production-ready image optimisation without infrastructure management.

**sa-portfolio**

[sa-portfolio](https://github.com/ChildishGirl/sa-portfolio) if you are looking for a great set of reference solutions, then **AWS Community Builder Anna Pastushko** has put together a really well put together and easy to follow set of six case studies.

![example reference architecture](https://raw.githubusercontent.com/ChildishGirl/sa-portfolio/refs/heads/main/images/customized-mlops-pipeline.png)

### AWS and Community blog posts

Before getting into the posts, there are a couple of notices that I want to share.

* **AWS Hero Colin Percival** has been building AMIs for FreeBSD for the past 16 years and is setting up a mailing list for discussions among people porting operating systems to and/or maintaining operating systems in EC2.  Please contact him directly at  [cperciva@FreeBSD.org](mailto:cperciva@FreeBSD.org) for details.
*  **AWS Community Builder Marko Bevc** wanted to share an update about the state of the [aws-vault](https://github.com/ByteNess/aws-vault) project (a tool to securely store and access AWS credentials in development environments). A community fork is now keeping this project going, so if you were familiar with this project from the past, then I am happy to say it continues to live.

**Community**

I spend time each week reading through posts from the AWS and open source communities, and I'm always impressed by the depth and variety of topics people are exploring. This week brought some particularly interesting contributions that I wanted to share with you.

On the Kubernetes and observability front, we saw several excellent deep dives. **AWS Community Builder Stéphane Noutsa** wrote about [Enhancing Your AWS EKS Cluster with Istio Service Mesh and Kiali Observability](https://dev.to/aws-builders/enhancing-your-aws-eks-cluster-with-istio-service-mesh-and-kiali-observability-49kk), exploring how Istio and Kiali can help manage microservices networking and visualise traffic patterns. **AWS Community Builder Tanushree Aggarwal** complemented this nicely with [Observability-Driven Kubernetes: A Practical EKS Demo](https://dev.to/aws-builders/observability-driven-kubernetes-a-practical-eks-demo-5gjp), demonstrating how to build a production-grade observability platform using Terraform. And speaking of observability, **AWS Community Builder Michael Uanikehi** showed you how you can use the Lambda Powertools open source tool to tackle a specific CloudWatch challenge in [Measuring What Matters: Adding Multiple Dimension Sets to AWS Lambda Powertools](https://dev.to/aws-builders/measuring-what-matters-adding-multiple-dimension-sets-to-aws-lambda-powertools-aob), showing how multi-dimensional metric aggregation solves real production monitoring challenges.

The AI agent space continues to heat up with some great posts. At re:Invent Strands Agents launched a TypeScript version of the framework, so it was great to see **AWS Community Hero Ryan** look at this in his post, [Typescript AI Agents](https://ryancormack.medium.com/typescript-ai-agents-1b4fec66a58d). **AWS Community Builder Jansen Ang** demonstrated [Building a Splunk Investigator Agent with Strands Agents and Amazon Bedrock AgentCore](https://dev.to/aws-builders/building-a-splunk-investigator-agent-with-strands-agents-and-amazon-bedrock-agentcore-53dc), connecting AI agents with Splunk for log analysis. **Martin Mueller** explored production-ready AI agents in his post [AWS Bedrock AgentCore - AI Agent Development from Local to Cloud](https://martinmueller.dev/aws-agentcore/), walking through the journey from local Docker development to cloud deployment. **Arun Thangavel** posted [Deploy Spring Apps With Amazon Bedrock Agent Core](https://builder.aws.com/content/37u4zYzqu6N2pkRC7fZPmKhJO32/deploy-spring-ai-apps-with-amazon-bedrock-agent-core) on Builder Centre that showed how to integrate Bedrock's AI capabilities into Spring Boot applications, while another post from **Jyri** explored [How Can Duckdb Help Strands Agent Work With Ephemeral Structured Data](https://builder.aws.com/content/36Nf2xol4BOklP70eEk3kUPHmQs/how-can-duckdb-help-strands-agent-to-work-with-ephemeral-structured-data), looking at what's the most efficient way to allow your Agent to work and explore with data, demonstrating DuckDB's analytical capabilities for agent workflows.

On the infrastructure and data processing side, **AWS Hero Johannes Konings** shared [Use a customized CDK bootstrap template](https://dev.to/aws-builders/use-a-customized-cdk-bootstrap-template-1ph3), showing how to add advanced security configurations to CDK deployments. **AWS Community Builder Aki** wrote an interesting comparison in [Lightweight ETL with AWS Glue Python Shell, chDB, and PyIceberg (Compared with DuckDB)](https://dev.to/aws-builders/lightweight-etl-with-aws-glue-python-shell-chdb-and-pyiceberg-compared-with-duckdb-5hcc), exploring different approaches to ETL pipelines and how to work around Lambda's execution time limits. **AWS Hero Colin Percival** shared an important update, [Patched FreeBSD AMIs](https://www.daemonology.net/blog/2026-01-20-Patched-FreeBSD-AMIs.html) that looks at how FreeBSD is now getting new AMIs for every security update. Finally, **Silvio Gissi** and **Mahesh Cherukumilli** addressed an important community need with [Valkey Helm: The new way to deploy Valkey on Kubernetes](https://valkey.io/blog/valkey-helm-chart/), explaining how the official Helm chart helps teams avoid deployment disruptions from Bitnami's policy changes.

Thanks to everyone who shared their knowledge this week! If you've written something you'd like featured in a future newsletter, please reach out as I love highlighting community contributions.

**GenAI**

* [Build durable AI agents with LangGraph and Amazon DynamoDB](https://aws-oss.beachgeek.co.uk/4ns) - outlines building production ready AI agents using LangGraph and Amazon DynamoDB's new DynamoDBSaver connector for durable state management and persistence [hands on]

* [Migrate MLflow tracking servers to Amazon SageMaker AI with serverless MLflow](https://aws-oss.beachgeek.co.uk/4o1) - guides how to migrate self-managed MLflow tracking servers to Amazon SageMaker AI's serverless MLflow using the Export Import tool for cost optimisation [hands on]

* [Build and deploy scalable AI agents with NVIDIA NeMo, Amazon Bedrock AgentCore, and Strands Agents](https://aws-oss.beachgeek.co.uk/4oa) - presents building production-ready AI agent systems using NVIDIA NeMo, Amazon Bedrock AgentCore, and Strands Agents for scalable enterprise deployment [hands on]

* [Deploying Small Language Models at Scale with AWS IoT Greengrass and Strands Agents](https://aws-oss.beachgeek.co.uk/4o7) - discusses deploying Small Language Models on edge devices using AWS IoT Greengrass for real-time manufacturing intelligence and scalable industrial AI applications [hands on]

![deploying llms on the edge](https://d2908q01vomqb2.cloudfront.net/f6e1126cedebf23e1463aee73f9df08783640400/2025/11/28/IOTB-901-slm-at-edge.png)

**Cloud Native**

* [Streamline your containerized CI/CD with GitLab Runners and Amazon EKS Auto Mode](https://aws-oss.beachgeek.co.uk/4o2) - showcases deploying GitLab Runners on Amazon EKS Auto Mode with EC2 Spot Instances to achieve enterprise scale CI/CD capabilities while reducing costs by up to 90% [hands on]

* [Part 2: Observing and scaling MLOps infrastructure on Amazon EKS](https://aws-oss.beachgeek.co.uk/4o3) - addresses comprehensive observability strategies for MLOps infrastructure on Amazon EKS, covering monitoring tools, scaling patterns, and unique challenges of machine learning workloads in Kubernetes environments [hands on]

* [Implementing assurance pipeline for Amazon EKS Platform](https://aws-oss.beachgeek.co.uk/4o4) - describes building comprehensive assurance pipelines for Amazon EKS platforms using six validation frameworks to ensure production-ready, compliant Kubernetes deployments [hands on]

* [Enhance Amazon EKS network security posture with DNS and admin network policies](https://aws-oss.beachgeek.co.uk/4o6) - unveils Amazon EKS's new DNS based and Admin network policies that enhance cluster security through centralised, domain-based access controls and cross-namespace policy management [hands on]

* [Deep dive: Streamlining GitOps with Amazon EKS capability for Argo CD](https://aws-oss.beachgeek.co.uk/4ob) - analyses Amazon EKS's new fully managed Argo CD capability that eliminates operational overhead for GitOps deployments across multi-cluster Kubernetes environments [hands on]

* [Simplify Kubernetes cluster management using ACK, kro and Amazon EKS](https://aws-oss.beachgeek.co.uk/4oc) - illustrates using ACK, kro, and Amazon EKS to streamline Kubernetes cluster management through GitOps-based automation and declarative YAML constructs [hands on]

**Data and Analytics**

* [How to Build and Backtest Systematic Trading Strategies with AWS Batch and Airflow](https://aws-oss.beachgeek.co.uk/4nv) - explores how to construct scalable systematic trading strategy backtesting infrastructure using AWS Batch, Airflow, and ClickHouse for quantitative hedge fund research workflows [hands on]

![architecture overview](https://d2908q01vomqb2.cloudfront.net/c5b76da3e608d34edb07244cd9b875ee86906328/2026/01/05/backtest-architecture2-1.png)

* [Enterprise scale in-place migration to Apache Iceberg: Implementation guide](https://aws-oss.beachgeek.co.uk/4no) - demonstrates implementing enterprise scale in-place migration from Apache Parquet data lakes to Apache Iceberg using DynamoDB orchestration for fault-tolerant, configurable transformations [hands on] 

* [Create and update Apache Iceberg tables with partitions in the AWS Glue Data Catalog using the AWS SDK and AWS CloudFormation](https://aws-oss.beachgeek.co.uk/4o9) - details how to automate Apache Iceberg table creation and management with partitions using AWS Glue Data Catalog, SDKs, and CloudFormation templates [hands on]

* [Building scalable AWS Lake Formation governed data lakes with dbt and Amazon Managed Workflows for Apache Airflow](https://aws-oss.beachgeek.co.uk/4nz) - covers building scalable AWS data lakes using Lake Formation governance with dbt transformations and Amazon MWAA orchestration for enterprise-grade data pipeline management

![solution architecture diagram](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2025/12/17/BDB-4834-arch-diag.png)

* [Managing Amazon OpenSearch UI infrastructure as code with AWS CDK](https://aws-oss.beachgeek.co.uk/4of) - shows how to automate Amazon OpenSearch UI dashboard creation across multiple environments using AWS CDK and Lambda functions for consistent, version-controlled analytics deployments [hands on]

* [Using the shared plan cache for Amazon Aurora PostgreSQL](https://aws-oss.beachgeek.co.uk/4nq) - reveals how Amazon Aurora PostgreSQL's Shared Plan Cache feature reduces memory consumption from 40GB to 400MB in high-concurrency environments by eliminating duplicate generic SQL plans [hands on]

* [Unlock Amazon Aurora's Advanced Features with Standard JDBC Driver using AWS Advanced JDBC Wrapper](https://aws-oss.beachgeek.co.uk/4nw) - looks at  how AWS Advanced JDBC Wrapper enhances standard JDBC drivers to unlock Amazon Aurora's cloud-native features like fast failover and IAM authentication [hands on]

* [Simplified management of Amazon MSK with natural language using Kiro CLI and Amazon MSK MCP Server](https://aws-oss.beachgeek.co.uk/4o5) - introduces Kiro CLI and Amazon MSK MCP Server to manage Apache Kafka clusters through natural language commands instead of complex APIs [hands on]

* [On-demand and scheduled scaling of Amazon MSK Express based clusters](https://aws-oss.beachgeek.co.uk/4oe) - walks through building a custom solution for dynamically scaling Amazon MSK Express clusters using CloudWatch metrics and intelligent rebalancing features [hands on]

**Other posts to check out**

* [.NET 10 runtime now available in AWS Lambda](https://aws-oss.beachgeek.co.uk/4nx) - announces AWS Lambda support for .NET 10 runtime with file-based apps, performance optimisations, and enhanced developer tooling for streamlined serverless development

* [Automating AWS SDK for Java v1 to v2 Upgrades with AWS Transform](https://aws-oss.beachgeek.co.uk/4ny) - explains how to automate AWS SDK for Java v1 to v2 upgrades using AWS Transform, addressing security requirements and performance improvements before v1's end-of-support deadline [hands on]

* [Modernize ASP.NET Web Forms UI to Blazor with AWS Transform](https://aws-oss.beachgeek.co.uk/4o8) - reviews how AWS Transform modernises .NET Framework Web Forms applications to cross-platform .NET 10 Blazor, reducing operating costs up to 40% [hands on]

* [Optimize Nextflow Workflows on AWS Batch with Mountpoint for Amazon S3](https://aws-oss.beachgeek.co.uk/4nt) - demonstrates how to optimise Nextflow genomic workflows on AWS Batch using Mountpoint for Amazon S3 to stream large reference files directly, eliminating costly staging bottlenecks [hands on]

**Case Studies**

* [How Bazaarvoice modernized their Apache Kafka infrastructure with Amazon MSK](https://aws-oss.beachgeek.co.uk/4np) - Examines how Bazaarvoice migrated from self-managed Apache Kafka to Amazon MSK, reducing operational overhead while maintaining high-performance streaming for their global reviews platform [case study]

* [MaiCoin case study: Blue/green upgrade from Amazon ElastiCache Redis to Valkey](https://aws-oss.beachgeek.co.uk/4od) - documents MaiCoin's successful blue/green deployment strategy for migrating from Amazon ElastiCache Redis to Valkey, achieving 20-33% cost savings with minimal downtime [case study]

* [How Salesforce migrated from Cluster Autoscaler to Karpenter across their fleet of 1,000 EKS clusters](https://aws-oss.beachgeek.co.uk/4nu) - Chronicles Salesforce's successful migration of their massive 1,000+ EKS cluster fleet from traditional Cluster Autoscaler to Karpenter for improved scaling efficiency [case study]

* [Telco Network Cloud (TNC) on Red Hat OpenShift Service on AWS (ROSA)](https://aws-oss.beachgeek.co.uk/4o0) - Looks at how to deploy Red Hat's Telco Network Cloud reference architecture for managing 4G/5G telecommunications infrastructure using ROSA on AWS [case study]

![architecture high level](https://d2908q01vomqb2.cloudfront.net/c097638f92de80ba8d6c696b26e6e601a5f61eb7/2025/12/30/Screenshot-2025-12-30-at-11.09.27%E2%80%AFAM.png)

* [How Slack achieved operational excellence for Spark on Amazon EMR using generative AI](https://aws-oss.beachgeek.co.uk/4nr) - highlights Slack's comprehensive monitoring framework using generative AI to optimise Apache Spark performance on Amazon EMR, achieving 30-50% cost reductions and 40-60% faster job completion times [case study]

### Quick updates

**Gradle**

Amazon Inspector scanning for Lambda functions and Elastic Container Registry (ECR) images now supports Java Gradle inventory and vulnerability scanning. This release also adds coverage for MySQL, MariaDB, PHP, Jenkins-core, 7zip (on Windows), and Curl/LibCurl.

The new Java Gradle support allows Inspector to scan Java dependencies based on gradle.lockfile content, providing comprehensive vulnerability assessments for Java applications. When you use Inspector to scan Lambda functions and ECR images, you will now see findings for the newly supported technologies.

These enhancements enable more accurate detection of vulnerabilities in packages installed outside of package managers, improving overall security coverage. You can start using these new features today in all AWS Regions where Amazon Inspector is available.

**Amazon Corretto**

Amazon announced quarterly security and critical updates for Amazon Corretto Long-Term Supported (LTS) versions of OpenJDK. Corretto 25.0.2, 21.0.10, 17.0.18, 11.0.30, and 8u482 are now available for download.

Amazon Corretto is a no-cost, multi-platform, production-ready distribution of OpenJDK. You can download Corretto 25, Corretto 21, Corretto 17, Corretto 11, or Corretto 8 from the Corretto home page, or get updates on Linux systems by configuring a Corretto Apt, Yum, or Apk repo.

**RabbitMQ**

Amazon MQ now supports certificate based authentication with mutual TLS for RabbitMQ brokers. RabbitMQ brokers can now perform authentication using X.509 client certificates with mutual TLS (mTLS). The RabbitMQ auth_mechanism_ssl plugin can be configured on brokers running RabbitMQ version 4.2 and above by making changes to the associated configuration file. To start using certificate based authentication, select RabbitMQ 4.2 when creating a new broker using the M7g instance type through the AWS Management console, AWS CLI, or AWS SDKs, then edit the associated configuration file with the required values. This plugin is available in all regions where Amazon MQ RabbitMQ 4 instances are available.

In more RabbitMQ news, Amazon MQ now supports HTTP based authentication for RabbitMQ brokers. RabbitMQ brokers can now perform authentication (determining who can log in) and authorisation (determining what permissions they have) by making requests to an HTTP server. This plugin can be configured on brokers running RabbitMQ 4.2 and above by making changes to the associated configuration file. To start using HTTP based authentication and authorisation, select RabbitMQ 4.2 when creating a new broker using the m7g instance type through the AWS Management console, AWS CLI, or AWS SDKs, then edit the associated configuration file. This plugin is available in all regions where Amazon MQ RabbitMQ 4 instances are available.

The final RabbitMQ update this month shares the good news that RabbitMQ 4 brokers can now connect to JMS applications through the RabbitMQ JMS Topic Exchange plugin and JMS client. The JMS topic exchange plugin is enabled by default on all RabbitMQ 4 brokers, allowing you to use the JMS client to run your JMS 1.1, JMS 2.0, and JMS 3.1 applications on RabbitMQ. You can also use the RabbitMQ JMS client to send JMS messages to an AMQP exchange and consume messages from an AMQP queue to interoperate or migrate JMS workloads to AMQP workloads.

**OpenSearch**

Amazon OpenSearch Service now supports AWS KMS customer managed keys (CMKs) and increased size for OpenSearch UI metadata. Amazon OpenSearch UI is a managed service for dashboards and operational analytics that provides a unified view across multiple data sources, including OpenSearch domains and collections, Amazon S3, Amazon CloudWatch, and AWS Security Lake.

You can now create new OpenSearch UI applications with metadata encrypted with your own CMKs, helping organisations meet regulatory and compliance requirements. This launch also increases the metadata size limit for saved objects in OpenSearch UI, enabling you to create and store complex queries, extensive visualisations, and large-scale dashboards.

CMK support and increased metadata size are available in all regions that OpenSearch UI is available.

**Apache Airflow**

You can now create Apache Airflow version 2.11 environments on Amazon Managed Workflows for Apache Airflow (MWAA). Apache Airflow 2.11 introduces several changes to help you prepare for upgrading to Apache Airflow 3.

Apache Airflow 2.11 introduces notable enhancements, such as new trigger-based scheduling for delta intervals, consistent reporting of metrics in milliseconds and other changes that will make it easy to migrate to Apache Airflow 3. MWAA now provides support for Python 3.12 that you can leverage in your workflows.

You can launch a new Apache Airflow 2.11 environment on Amazon MWAA with just a few clicks in the AWS Management Console in all currently supported Amazon MWAA regions.

**MySQL**

Amazon RDS for MySQL now supports community MySQL Innovation Release 9.5 in the Amazon RDS Database Preview Environment, allowing you to evaluate the latest Innovation Release on Amazon RDS for MySQL. You can deploy MySQL 9.5 in the Amazon RDS Database Preview Environment which provides the benefits of a fully managed database, making it simpler to set up, operate, and monitor databases.

MySQL 9.5 is the latest Innovation Release from the MySQL community. MySQL Innovation releases include bug fixes, security patches, as well as new features. MySQL Innovation releases are supported by the community until the next innovation minor, whereas MySQL Long Term Support (LTS) Releases, such as MySQL 8.0 and MySQL 8.4, are supported by the community for up to eight years.

Amazon RDS Database Preview Environment supports both Single-AZ and Multi-AZ deployments on the latest generation of instance classes. Database instances are retained for a maximum of 60 days and are automatically deleted after the retention period. Database snapshots created in the Preview Environment can only be used within the Preview Environment. Preview Environment database instances are priced the same as production RDS instances in the US East (Ohio) Region.

**PostgreSQL**

Amazon RDS for PostgreSQL announces Extended Support minor versions 12.22-rds.20251114 and 11.22-rds.20251114. We recommend upgrading to these versions to fix known security vulnerabilities and bugs in prior PostgreSQL versions. Amazon RDS Extended Support provides up to three years to upgrade to a new major version, helping you meet business requirements. During Extended Support, Amazon RDS provides critical security and bug fixes for PostgreSQL databases after the community ends support for a major version. You can leverage automatic minor version upgrades to automatically upgrade databases to more recent minor versions during scheduled maintenance windows. Amazon RDS for PostgreSQL is available in all commercial and gov cloud regions.

Amazon Aurora PostgreSQL-Compatible Edition now supports PostgreSQL versions 17.7, 16.11, 15.15, 14.20 and 13.23. The update includes PostgreSQL community improvements and bug fixes, plus Aurora-specific enhancements. The release includes improvements to Blue Green deployments with reduced switchover times by limiting new commits on the primary instance. There are also enhancements to Query Plan Management (QPM) and improved instance recovery times by optimising commit log loading during database recovery. To use the new versions, create a new Aurora PostgreSQL-compatible database in the Amazon RDS Management Console or upgrade your existing database. These releases are available in all commercial AWS Regions and AWS GovCloud (US) Regions.

**.NET**

AWS Lambda now supports creating serverless applications using .NET 10. Developers can use .NET 10 as both a managed runtime and a container base image, with AWS automatically applying updates to the managed runtime and base image as they become available.

.NET 10 is the latest long-term support release of .NET and is expected to be supported for security and bug fixes until November 2028. This release provides Lambda developers with access to the latest .NET features, including file-based apps. It also includes support for Lambda Managed Instances, enabling you to run Lambda functions on Amazon EC2 instances while maintaining serverless operational simplicity.

Powertools for AWS Lambda (.NET) also supports .NET 10. You can use the full range of AWS deployment tools, including the Lambda console, AWS CLI, AWS SAM, AWS CDK, and AWS CloudFormation to deploy and manage serverless applications written in .NET 10. The .NET 10 runtime is available in all Regions, including AWS GovCloud (US) Regions and China Regions.

**Apache Kafka**

Amazon Managed Streaming for Apache Kafka (MSK) now supports Apache Kafka version 3.9 for Express Brokers. This release introduces support for KRaft (Kafka Raft), Apache Kafka's new consensus protocol that eliminates the dependency on Apache ZooKeeper for metadata management.

KRaft shifts metadata management in Kafka clusters from external Apache ZooKeeper nodes to a group of controllers within Kafka. This allows metadata to be stored and replicated as topics within Kafka brokers, resulting in faster metadata propagation. New Express Broker clusters created using Kafka v3.9 will automatically use KRaft as the metadata management mode. The ability to upgrade existing clusters to v3.9 will be available in a future release. Amazon MSK Express Brokers with Kafka v3.9 are available in all AWS regions where MSK Express is supported.

**AWS Neuron SDK**

AWS announces Neuron SDK 2.27.0, introducing support for Trainium3 UltraServer with expanded open source components. Neuron introduces the Neuron Explorer tools suite, Enhanced NKI with open source NKI Compiler built on MLIR (private beta), the NKI Library of optimised kernels, native PyTorch support through TorchNeuron (private beta), and Neuron DRA for Kubernetes-native resource management (private beta).  These updates enable standard frameworks to run unchanged on Trainium, removing barriers for researchers to experiment and innovate. For developers requiring deeper control, the enhanced Neuron Kernel Interface (NKI) Beta 2 provides direct access to hardware-level optimisations, enabling customers to scale AI workloads with improved performance. 

The new SDK version is available in all AWS Regions supporting Inferentia and Trainium instances, offering enhanced performance and monitoring capabilities for machine learning workloads.

**Ubuntu**

Amazon WorkSpaces Applications now offers support for Ubuntu Pro 24.04 LTS on Elastic fleets, enabling Independent Software Vendors (ISVs) and central IT organisations to stream Ubuntu desktop applications to users while leveraging the flexibility, scalability, and cost-effectiveness of the AWS Cloud.

Amazon WorkSpaces Applications is a fully managed, secure desktops and applications streaming service that provides users with instant access to their desktops and applications from anywhere. Within Amazon WorkSpaces Applications, Elastic fleet is a serverless fleet type that lets you stream desktop applications to end users from an AWS-managed pool of streaming instances without needing to predict usage, create and manage scaling policies, or create an image. To get started, sign into the WorkSpaces Applications management console and select your AWS Region of choice. Amazon WorkSpaces Applications offers pay-as-you-go pricing.

**InfluxDB**

Amazon Timestream for InfluxDB now offers a restart API for both InfluxDB versions 2 and 3. This capability enables customers to trigger system restarts on their database instances directly through the AWS Management Console, API, or CLI to streamline operational management of their time-series database environments.

With the restart API, customers can perform resilience testing to validate their application's behaviour during database restarts and address health-related issues without requiring support intervention. This feature enhances operational flexibility for DevOps teams managing mission-critical workloads, allowing them to implement more comprehensive testing strategies and respond faster to performance concerns by providing direct control over database instance lifecycle operations. The restart capability is available in all Regions where Timestream for InfluxDB is offered.

### Videos of the month

**Look ma, no hands: Automating Open-Source Geospatial Infrastructure with AWS CDK (IaC)**

Hot off the FOSS4G 2025 event, **Subodh Dangwal** talked about how Abley’s mapping stack leverages AWS and the AWS Cloud Development Kit (CDK) to automate, standardise, and scale geospatial infrastructure. Discover how reusable CDK library enables rapid, environment-driven deployment of high-performance mapping services that power the Abley  SafeSystem  and geospatial APIs.

{{< youtube eJDuWbbY3A4 >}}

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes: Seth Art, Damon Cortesi, Mehmet Ayberk, Noureldin Ehab, Hüseyin Babal, Michael Walmsley, Gurgen, Simon Hanmer, Subodh Dangwal, Silvio Gissi, Mahesh Cherukumilli, Ryan Cormack, Johannes Konings, Aki, Stéphane Noutsa, Tanushree Aggarwal, Jansen Ang, Arun Thangavel, Jyri, Martin Mueller, Michael Uanikehi,  Colin Percival, Marko Bevc, Aarjvi Desai, Aarthi Srinivasan, Abdullahi Olaoye, Abhilasha Agarwal, Abhishek Sawarkar, Alexandra Huides, Ali Bokhari, Amir Majlesi, Amit Maindola, Ankit Mishra, Anuj Butail, Anurag Gajam, Aravind Marthineni, Arghya Banerjee, Avijit Goswami, Badrish Shanbhag, Brent Everman, Carlos Santana, Cathy Lai, Charles Hsiao, Charlie Chiu, Chirag Dave, Chris Smith, Christian Silva, Dave Cramer, David Hache, David Pallmann, Elamaran Shanmugam, Ganga Hiremath, HC Lo, Henrique Graca, Isha Dua, Islam Mahgoub, Jacky Wu, Jeremy Cowan, Jesse Butler, Johnny Yu, Jonathan Tuliani, Jungkook Lee, Kalyan Janaki, Ken Cho, Kosti Vasilakakis, Kumudhan Cherarajan, Lee Hannigan, Luis Orus, Markos Kandylis, Mayur Shetty, Melody Lin, Michael Mueller, Mihir Borkar, Mimi Wang, Min Wang, Mithilesh Satapathy, Muralidhar Reddy, Niall Thomson, Nilanjana Mukherjee, Oleh Khoruzhenko, Ozan Cihangir, Pankaj Walke, Paul-Andre Bisson, Prateek Kakirwar, Pratik Das, Qu Chen, Rahul Easwar, Rahul Gidwani, Rakshith Rao, Ramesh Eega, Ramesh Mathikumar, Ranjit Rajan, Roland Odorfer, Ryan Niksch, Sagar Murthy, Sana Jawad, Sandhya Khanderia, Sanjeev Ganjihal, Satish Patil, Shalaka Dhayatkar, Simon Murray, Souvik Bhattacherjee, Stephen Wood, Subham Rakshit, Sundar Shanmugam, Sébastien Allamand, Tayven Taylor, Venugopalan Vasudevan, Vikram Venkataraman, Vivek Bhadauria, and Zhongnan Su.

### Stay in touch with open source at AWS

Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) for more open source goodness.

One of the pieces of feedback I received was to create a repo where all the projects featured in this newsletter are listed. Where I can hear you all ask? Well as you ask so nicely, you can meander over to[ newsletter-oss-projects](https://aws-oss.beachgeek.co.uk/3l8).

Made with ♥ from DevRel