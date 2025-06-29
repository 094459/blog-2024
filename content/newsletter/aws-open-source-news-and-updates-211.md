---
title: 'AWS open source newsletter #211'
date: '2025-06-28'
tags : [ oss-newsletter, aws open source, Apache Airflow, MWAA, Swift, Amazon Q CLI, Cedar, GNOME, Strands Agents, Valkey, CDK, Pydantic, Kyverno, OPA Gatekeeper, Karpenter, Kubernetes, Amazon EKS, Apache Kafka, Apache Iceberg, Trino, Apache Flink, Amazon EMR, Apache Spark, HBase, RocksDB, OpenLineage, dbt, MySQL, MariaDB, PostgreSQL, RabbitMQ, AWS Amplify, Tanstack, Amazon Linux 2023, .NET Aspire, OpenSearch, AWS Tools for PowerShell, Prometheus, Mountpoint for Amazon S3, OpenZFS, Powertools for AWS Lambda, Red Hat Enterprise Linux ]
canonicalUrl: "https://dev.to/aws/aws-open-source-newsletter-211-188"
---

##  Edition #211 - June 2025

Welcome to issue #211 of the AWS open source newsletter, the newsletter where I try and provide you the best open source on AWS content.  I was super humbled by [**AWS Hero Lee Gilmore**](https://www.linkedin.com/posts/lee-james-gilmore_aws-serverless-awslambda-activity-7342077758648270848-_Ilu) earlier this month, who gave this newsletter a shoutout - thank you! (and make sure you check out his own newsletter, [the Serverless Advocate Newsletter](https://serverlessadvocate.substack.com/p/42-security-updates-galore?r=rad0z&utm_campaign=post&utm_medium=web&triedRedirect=true)). Please please please take 1 minute to [complete this short survey](https://www.pulse.aws/promotion/10NT4XZQ) - feedback is a gift, and your gifts help keep this newsletter going in the right direction.

As always, this edition has more great new projects to check out. [re:Inforce](https://reinforce.awsevents.com/) happened in June, so its perhaps not surprising that this month we see a large number of security related projects that were surfaced up. Those projects and tools are all super useful, from providing password managers, auditing tools for your AWS resources, or tools to help you analyse your IAM policies, there is something for everyone. It's not all security stuff though, we have the usual collection of generative AI projects this month, including some useful MCP Servers that I think you will find useful, a nice GUI wrapper around Amazon Q CLI, and a very nice tool top help you analyse your Amazon CloudWatch logs. Definitely check that one out.

The projects will keep you busy until next month for sure, but we also have plenty of reading material in this months newsletter. In this edition we have featured projects that include Apache Airflow, Swift, Amazon Q CLI, Cedar, GNOME, Strands Agents, Valkey, CDK, Pydantic, Kyverno, OPA Gatekeeper, Karpenter, Kubernetes, Apache Kafka, Apache Iceberg, Trino, Apache Flink, Amazon EMR, Apache Spark, HBase, RocksDB, OpenLineage, dbt, MySQL, MariaDB, PostgreSQL, RabbitMQ, AWS Amplify, Tanstack, Amazon Linux 2023, .NET Aspire, OpenSearch, AWS Tools for PowerShell, Prometheus, Mountpoint for Amazon S3, OpenZFS, Powertools for AWS Lambda, and Red Hat Enterprise Linux.

Check out the list of contributors at the end of the newsletter, and as always, get in touch if you want me to feature your projects in this open source newsletter. 

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution. The projects mentioned here do not represent any formal recommendation or endorsement, I am just sharing for greater awareness as I think they look useful and interesting!*

### Tools

**RunnaVault**

[RunnaVault](https://aws-oss.beachgeek.co.uk/4eq) is a secure, serverless password management application built using AWS free-tier services and a React frontend. It enables users to create, manage, and share encrypted secrets (e.g., passwords) with individuals or groups, leveraging AWS Cognito for authentication, DynamoDB for storage, and KMS for encryption. Check out the repo for screenshots of what the app looks like as well as more technical implementation details (which you can deploy via OpenTofu/Terraform). I wish more READMEs would do this, but they also include some estimated costs of what it might cost to run this project in your AWS Account. Go check it out.

**yes3-scanner**

[yes3-scanner](https://aws-oss.beachgeek.co.uk/4er) is the first in a series of projects from the folks at **Fog Security**, which scans an AWS Account for potential S3 security issues such as access issues such as Public Access, preventative S3 Security Settings, additional security such as encryption, and Ransomware Protection, Data Protection, and Recovery.

**aws-managed-kms-keys**

[aws-managed-kms-keys](https://aws-oss.beachgeek.co.uk/4es) more goodness from the folks at **Fog Security**, this time providing a repo that provides a listing of AWS Managed KMS Keys and their associated policies in /reference_key_policies. There's a periodic scheduled job that will run and update the listings and data. The README does note that *"AWS managed keys are a legacy key type that are no longer being created for new AWS services as of 2021"* so you might not expect to see more AWS managed keys outside of the ones already listed

**finders-keypers**

[finders-keypers](https://aws-oss.beachgeek.co.uk/4et) is a command line tool that will explore your AWS account and kook for direct connections for KMS Keys and resources in your account. This tool supports both AWS Customer Managed KMS Keys and AWS Managed KMS Keys (with some additional details in the README that you should check out). Typical use cases where this tool is helpful includes security and audit for KMS Key and Resources, Data Protection with Encryption, discovering blast radius of a specific KMS Key, changing a KMS Key or rotating key material, checking Default Settings in AWS that create new resources with the KMS Key, and audit of your resources that a KMS Key may grant access to. README provide examples of how to run the cli against some of those use cases. Very nice tool indeed.

**iam-collect**

[iam-collect](https://aws-oss.beachgeek.co.uk/4ew) is a tool from **David Kerber** that helps you collect IAM information from all your AWS organization, accounts, and resources. This is built to run out of the box in simple use cases, and also work in terribly oppressive environments with a little more configuration. If you want to analyze IAM data at scale this is what you've been looking for.

**iam-lens**

[iam-lens](https://aws-oss.beachgeek.co.uk/4ev) is another tool from **David Kerber**, which builds upon iam-collect, and helps you evaluate your AWS IAM policies offline. It. helps you get visibility into the IAM permissions in your AWS Organizations and accounts. It will use your actual AWS IAM policies (downloaded via iam-collect) and evaluate the effective permissions. Hat tip to Eduard Agavriloae whose [social media](https://www.linkedin.com/posts/activity-7336269672012525569-C_Ao/) message tipped me off.

**type-safe-cdk-env**

[type-safe-cdk-env](https://aws-oss.beachgeek.co.uk/4f4) is from **AWS Community Builder Dakota Lewallen** and provides a TypeScript library that provides type-safe environment configuration for AWS CDK stacks using Zod for schema validation (Helper function to parse JSON files into environment variables within CDK stacks). Check out the README for example code and more details.

**cdk-sops-secrets**

[cdk-sops-secrets](https://aws-oss.beachgeek.co.uk/4ex) helps you create secret values in AWS with infrastructure-as-code easily by providing a CDK construct library that facilitate syncing SOPS-encrypted secrets to AWS Secrets Manager and SSM Parameter Store. It enables secure storage of secrets in Git repositories while allowing seamless synchronisation and usage within AWS. Even large sets of SSM Parameters can be created quickly from a single file. Detailed README with plenty of examples of how you can use this. Very nice.

**deploy-time-build**

[deploy-time-build](https://aws-oss.beachgeek.co.uk/4ey) is an AWS CDK L3 construct that allows you to run a build job for specific purposes. Currently this library supports the following use cases: 1/ Build web frontend static files, 2/Build a container image, and 3/Build Seekable OCI (SOCI) indices for container images. Nice README with plenty of example code on how you can use against these use cases.

**secret**

[secret](https://aws-oss.beachgeek.co.uk/4ez) is from **AWS Hero Matthew Bonig** and provides a CDK Construct to create Secrets Manager secrets without unexpectedly recreating them (avoiding the issue when you update the generateSecretString property, the secret gets recreated!). Detailed README including the design philosophy.

**cdk-diff-action**

[cdk-diff-action](https://aws-oss.beachgeek.co.uk/4f0) from **Cory Hall**, provides a GitHub Action to run "cdk diff" on your PRs to track infrastructure changes.

**amazon-q-developer-cli-webui**

[amazon-q-developer-cli-webui](https://aws-oss.beachgeek.co.uk/4f5) is a very nice project from **AWS Community Builder Gabriel Koo** that allows you to run Amazon Q CLI via a web ui. He put together a post that explains the itch he was trying to scratch, and I have to say that this is on my weekend list of projects to try out. Go read the post, [Why I Built a Web UI for Amazon Q Developer CLI (And How I Vibe-Coded It)](https://dev.to/aws-builders/why-i-built-a-web-ui-for-amazon-q-developer-cli-and-how-i-vibe-coded-it-54d6). Nice work Gabriel!

**amazon-q-vibes-memory-banking**

[amazon-q-vibes-memory-banking](https://aws-oss.beachgeek.co.uk/4fd) is from **AWS Serverless Community Builder Nicola Cremaschini** who shares his approach to using AI Coding Assistants like Amazon Q Developer, to provide more consistent outcomes. The Q-Vibes framework helps maintain context across AI assistant sessions through 5 lightweight files, enabling quick prototype development without losing momentum between sessions. Give it a go and see how you get on.

**aws-lambda-mcp-cookbook**

[aws-lambda-mcp-cookbook](https://aws-oss.beachgeek.co.uk/4fc) is a repository from **AWS Hero Ran Isenberg** that provides a working, deployable, open source-based, serverless MCP server blueprint with an AWS Lambda function and AWS CDK Python code with all the best practices and a complete CI/CD pipeline.  Checkout the README for details of how this is put together, and how to get started. 

**finch-mcp-server**

[finch-mcp-server](https://aws-oss.beachgeek.co.uk/4ep) is the source code for the Finch MCP Server,  that enables generative AI models to build and push container images through finch cli leveraged MCP tools. It currently can build container images using Finch, push those images onto container registries (like Amazon ECR) creating them if needed, and manage all your Finch configuration files. The json configuration files that you will need for your MCP Clients [can be found here](https://awslabs.github.io/mcp/servers/finch-mcp-server/), together with additional info on dependencies and how this works.

**strands-ts**

[strands-ts](https://aws-oss.beachgeek.co.uk/4ed) is an experimental SDK for Strands for TypeScript developers from AWS Serverless Community Builder **Ryan Cormack**.  It is an AI generated migration of the Python SDK to TypeScript, using the same architecture and design principles. It is not a direct translation but rather a reimagining of the SDK in TypeScript, leveraging its features and idioms. As he [points out](https://www.linkedin.com/posts/ryancormack_github-ryancormackstrands-ts-activity-7343022012941975552-ANWU) in his social media post:

> 🤖 Inspired by the power of today's coding agents, I decided to see if AI could translate it. The result? A semi/mostly/barely functional, AI-generated Strands SDK in Typescript! 🤔 
>
> This unofficial repo mirrors the API of the original, complete with support for agents, built-in tools, custom tools and MCP. It's a testament to the quality of the original SDK that an AI could so effectively replicate its structure and style in a new language. Please don't use this repo for anything - it's missing a ton of stuff (not least a human reviewing it) and will probably break.

**cloudwatch-logs-analyzer**

[cloudwatch-logs-analyzer](https://aws-oss.beachgeek.co.uk/4f2) is an interesting tool from **AWS Community Builder Hafiz Syed Ashir Hassan** that uses Amazon Agent Strands to analyse CloudWatch logs, identify errors, and provide solutions based on either its own knowledge or a connected knowledge base. He has put together a blog post to help you get started, [Automating CloudWatch Log Analysis with Amazon Strands Agent: Meet the CloudWatch Analyzer](https://aws-oss.beachgeek.co.uk/4f3). A project to check out, dive into the README which provides more details and a sample screenshot of what this looks like.

### Demos, Samples, Solutions and Workshops

**wio-from-diagram-to-code-with-amazon-q-developer**

[wio-from-diagram-to-code-with-amazon-q-developer](https://aws-oss.beachgeek.co.uk/4eu) is a repo from **AWS Community Builder Olivier Lemaitre** that provides an extensive set of tutorials and labs he has put together to support a number of blog posts he has written, on how to go from diagram to code using AI Coding Assistants like Amazon Q Developer. These are detailed and very well done, so highly recommend you check these out.

**strands-serverless**

[strands-serverless](https://aws-oss.beachgeek.co.uk/4f1) is some sample code from my colleague **Didier Durand** that provides a serverless implementation of Strands Agents. This first experiment is the composition of Strands Agents with Chainlit (web-based interface) in one bundle. It delivers a complete AI agent in one Docker image running as an Amazon Lightsail virtual cloud server. He shared more info in [his social post here](https://www.linkedin.com/posts/ddurand_aws-strandsagents-agenticai-activity-7340286767784161280-vbRL)


### AWS and Community blog posts

**This weeks essential reading**

Here are the posts that I think are essential reads, so start here. We have more than we usually do, but thought these were all essential reads this month.

* [Best practices for upgrading Amazon MWAA V1.x to V2.x](https://aws-oss.beachgeek.co.uk/4e9) - if you are looking to move from earlier versions of Apache Airflow, you should check out this blog post to explore best practices for upgrading your Amazon MWAA environment and provide a step-by-step guide to seamlessly transition to the latest version [hands on]

* [Using Swift with Amazon Q CLU](https://aws-oss.beachgeek.co.uk/4ee) - my colleague Sebastien shares a great gist that you can use with Amazon Q CLI to get much better results as a Swift Developer - [check out](https://www.linkedin.com/posts/sebastienstormacq_swiftlang-amazonq-aicoding-activity-7342928170783825922-BsIF) the original social post with links to a deep dive post [hands on]

* [Secure your Express application APIs in 5 minutes with Cedar](https://aws-oss.beachgeek.co.uk/4dw) - announced the release of [authorization-for-expressjs](https://github.com/cedar-policy/authorization-for-expressjs), an open source package that simplifies using the Cedar policy language and authorisation engine to verify application permissions. This release allows developers to add policy-based authorisation to their Express web framework APIs within minutes - very cool! [hands on]

* [Introducing Cedar Analysis: Open Source Tools for Verifying Authorization Policies](https://aws-oss.beachgeek.co.uk/4dz) - looks at a new open source toolkit for developers that makes it easier for everyone to verify the behaviour of their Cedar policies - useing Satisfiability Modulo Theories (SMT) to reason about policies [hands on]

* [Using Strands Agents with Claude 4 Interleaved Thinking](https://aws-oss.beachgeek.co.uk/4e0) -  provides some examples of what you can build with Claude 4 interleaved thinking feature with Strands to further simplify how you write AI agents to solve complex tasks with tools [hands on]

* [GNOME has a new infrastructure partner: welcome AWS!](https://aws-oss.beachgeek.co.uk/4e4) - in case you missed this, GNOME share some of the improvements they have made as a result of our migration to the cloud

* [Introducing AWS API models and publicly available resources for AWS API definitions](https://aws-oss.beachgeek.co.uk/4e7) - shares news about  a new publicly available source of API models for Amazon Web Services (AWS),  which includes a definitive, up-to-date source of Smithy API models that define AWS public interface definitions and behaviours [hands on]

* [MCP OAuth on AWS Lambda with WorkOS](https://dev.to/aws-builders/mcp-oauth-on-aws-lambda-with-workos-129) - is a post from **AWS Community Builder szymon-szym** that shows you how to implement MCP OAuth, in this case using a third party provider (WorkOS) - loved this! [hands on]

**Community**

Each month I spend time reading posts from across the AWS community on open source topics. In this section I share what personally caught my eye and interest, and I hope that many of you will also find them interesting.

I want to start this issue by sharing info about **AWS Community Builder Maandeep Singh's** book (co-author), [System Design on AWS](https://oreil.ly/ruQbc), which includes lots of open source technologies (Kubernetes, Valkey, and more). If you are looking for a good book on AWS, why not check it out.

[Strands Agents](https://aws-oss.beachgeek.co.uk/4eh) is one of the hottest open source projects at the moment, that takes a simple yet powerful SDK that takes a model-driven approach to building and running AI agents. Not surprisingly, there has been a lot of great content appearing from the AWS Community to help you understand and get started with this. My colleague **Veliswa Boya** put together [I built a city explorer using the Strands Agents SDK](https://dev.to/aws/i-built-a-city-explorer-using-the-strands-agents-sdk-4n9b) providing a quick guide on how you can get started, extending an application she had built previously.  **Laura Salinas** also shared her experiences in the post [First Impressions with Strands Agents SDK](https://dev.to/aws/first-impressions-with-strands-agents-sdk-4hha).  Long time contributor to this newsletter **Gary Stafford** is on a hot streak, creating more great content, this time on Strands Agents. In [Introducing AWS Strands Agents: A New Paradigm in AI Agent Development](https://aws-oss.beachgeek.co.uk/4ei), after a quick primer he shows you how to create a Perplexity-like web search agent using Strands Agents and Amazon Bedrock foundation models, including Anthropic Claude Sonnet 4 and Amazon Nova Premier. Following that, he dives into Model Context Protocol (MCP), showing you how Stands Agents and MCP help orchestrate searches across multiple third-party APIs in the post, [AWS Strands Agents: Building and Connecting Your First MCP Server](https://aws-oss.beachgeek.co.uk/4ej).

We are not yet quite finished with Strands Agents. If you are looking at the Agent2Agent (A2A) protocol that allows you to orchestrate multiple agents (and which was recently donated to the Linux Foundation, yay!), then check out **Jagdeep Singh Soni's** post, [Agent Collaboration: Strands Agents, MCP, and the Agent2Agent Protocol](https://aws-oss.beachgeek.co.uk/4ek). **Todd Sharp** put together a nice walkthrough of how he used the Stands Agent SDK to create clips from a source You Tube link in the post, [Auto-Generating Clips for Social Media from Live Streams with the Strands Agents SDK](https://dev.to/aws/auto-generating-clips-for-social-media-from-live-streams-with-the-strands-agents-sdk-1kkj). The last Strands Agents post (honest!) is from **Dave Bechberger** who shares how you can leverage the Strands Agent SDK with Amazon Neptune to build and interact with a knowledge graph in his post, [Build a Knowledge Graph with Amazon Neptune and the Strands Agent SDK](https://aws-oss.beachgeek.co.uk/4el). Sticking within the field of generative AI, **Agam** showed you how to build AI Agents using self hosted models in his post (and accompanying video), [Build AI agents with Self Hosted Models with Tensorfuse + CrewAI](https://aws-oss.beachgeek.co.uk/4em). **Arjun kumar Giri** and **Jiaping Zeng** collaborated on [Unlocking agentic AI experiences with OpenSearch](https://aws-oss.beachgeek.co.uk/4en) with a nice walk through on how you can integrate the Amazon Q Developer CLI with OpenSearch’s agentic AI tools using MCP. I liked this one, and its on my todo list.

There was a number of important posts for AWS CDK fans this month, starting with **AWS Hero Rehan van der Merwe** who shares his experiences and tips for migrating from CDK Pipelines to CDK Express Pipelines in the post, [Migrate from CDK Pipelines to CDK Express Pipeline](https://aws-oss.beachgeek.co.uk/4ef). Following that is **AWS Hero Kenta Goto** who walks you through the CDK Toolkit Library, a library that allows you to directly incorporate CDK deployment and other operations into TypeScript programs for execution, in the post [Understanding CDK Toolkit Library: Comparing with CDK CLI](https://dev.to/aws-heroes/understanding-cdk-toolkit-library-comparing-with-cdk-cli-1k2b). Not content with just one post, he followed that with another post, [Using AWS CDK Property Injectors](https://dev.to/aws-heroes/using-aws-cdk-property-injectors-2mo5) that takes a look at what CDK Property Injectors are and how you can use them. Both are essential reads if you are a CDK geek. The final CDK related post in this round up comes from **AWS Community Builder Joris Conijn** who addresses some pain points he had during one of the projects he was working on, and how he addressed it. Go read his post, [Fixing oversized artifacts AWS CDK Pipelines](https://dev.to/aws-builders/fixing-oversized-artifacts-aws-cdk-pipelines-33nc)

On a non related AWS topic, but still something that I thought was worth sharing is **AWS Community Builder Damien Jones** who put together [Python Data Validation And Observability As Code With Pydantic](https://aws-oss.beachgeek.co.uk/4eg) which I found to be a useful primer on this essential Python library as he walks you through a musical example.  From data we move to cloud native, as **AWS Community Builder Ige Adetokunbo Temitayo** provides his take on how you can use open source tools like Kyverno and OPA Gatekeeper to keep your Kubernetes workloads secure in his post, [Simplify Kubernetes Security With Kyverno and OPA Gatekeeper](https://dev.to/aws-builders/simplify-kubernetes-security-with-kyverno-and-opa-gatekeeper-11o2). If you are interested in Amazon EKS Auto Mode automation, then **AWS Community Builders Trevor Roberts Jr** put something that you might want to read, [Automating EKS Auto Mode Pod Subnet Range Customization with EKS Node Classes, Karpenter Node Pools, and Terraform ](https://dev.to/aws-builders/automating-eks-auto-mode-pod-subnet-range-customization-with-eks-node-classes-karpenter-node-4nkg).  To finish up this month, we have **AWS Community Builder Binaya Sharma** who walks you through how you can migrate self managed Kubernetes add-on's in your Clusters to Amazon EKS managed in the post, [Migrate Self-Managed add-on to EKS Managed ](https://dev.to/aws-builders/migrate-self-managed-add-on-to-eks-managed-4hjp).

**Cloud Native**

* [Announcing the new AWS CDK EKS v2 L2 Constructs](https://aws-oss.beachgeek.co.uk/4do) - takes a look at new L2 constructs for Amazon EKS, sharing some of the rational behind this and then diving in and showing you how to use them [hands on]

* [Deep Dive: Amazon EKS Dashboard for Visibility into Multi-Cluster Operations and Governance]() - looks at the  Amazon Elastic Kubernetes Service (Amazon EKS) Dashboard, providing a centralised interface to get visibility and insights from your Kubernetes clusters - warning, graph overload!

**Data and Analytics**

* [Build a multi-Region session store with Amazon ElastiCache for Valkey Global Datastore](https://aws-oss.beachgeek.co.uk/4eb) - provides you with a solution using Amazon ElastiCache for Valkey and Amazon ElastiCache for Valkey Global Datastore to build a unified database caching layer with cross region replication for your applications [hands on]

* [Stream data from Amazon MSK to Apache Iceberg tables in Amazon S3 and Amazon S3 Tables using Amazon Data Firehose](https://aws-oss.beachgeek.co.uk/4dn) - demonstrates two approaches for data streaming from Amazon MSK to data lakes using Firehose: direct streaming to Iceberg tables in Amazon S3, and streaming to S3 Tables [hands on]
* [Query Amazon S3 Tables from open source Trino using Apache Iceberg REST endpoint](https://aws-oss.beachgeek.co.uk/4e1) - walks you through how to integrate Trino with S3 Tables [hands on]
* [New: Improve Apache Iceberg query performance in Amazon S3 with sort and z-order compaction](https://aws-oss.beachgeek.co.uk/4f8) - shows you how to use sort and z-order compaction to improve Apache Iceberg query performance in Amazon S3 Tables and general purpose S3 buckets [hands on]
* [Build a secure serverless streaming pipeline with Amazon MSK Serverless, Amazon EMR Serverless and IAM](https://aws-oss.beachgeek.co.uk/4ea) -  provides an end-to-end solution for processing data from MSK Serverless using an EMR Serverless Spark Streaming job, secured with IAM authentication [hands on]

* [Enhancing data durability in Amazon EMR HBase on Amazon S3 with the Amazon EMR WAL feature](https://aws-oss.beachgeek.co.uk/4ec) - dives into new Amazon EMR Write-Ahead Log (WAL) feature that allows you to improve durability of your Amazon EMR HBase on S3 clusters [hands on]

* [How Nexthink built real-time alerts with Amazon Managed Service for Apache Flink](https://aws-oss.beachgeek.co.uk/4e3) - provides a case study from Nexthink’s journey as they implemented a new real-time alerting system using Amazon Managed Service for Apache Flink, exploring the architecture, the rationale behind key technology choices, and more

![The following diagram illustrates how we join VDI metrics with monitor configurations, aggregate data using sliding time windows, and evaluate threshold rules, all within Apache Flink.](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2025/06/07/image-3-8-1024x325.png)

* [RocksDB 101: Optimizing stateful streaming in Apache Spark with Amazon EMR and AWS Glue](https://aws-oss.beachgeek.co.uk/4dq) - explores RocksDB as the new state store implementation in Apache Spark Structured Streaming, looking at key features and demonstrating its implementation using Spark on Amazon EMR and AWS Glue [hands on]
* [Capture data lineage from dbt, Apache Airflow, and Apache Spark with Amazon SageMaker](https://aws-oss.beachgeek.co.uk/4fb) - walks you through how to use OpenLineage to push data lineage events programmatically from tools supporting the OpenLineage standard like dbt, Apache Airflow, and Apache Spark [hands on]
* [Centralize Apache Spark observability on Amazon EMR on EKS with external Spark History Server](https://aws-oss.beachgeek.co.uk/4e8) - shows how you can centralise Apache Spark observability using the Spark History Server (SHS) running on Amazon EMR on EKS [hands on]

![solution overview](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2025/05/22/BDB-4471-001-architecture.png)

* [Implement row-level security in Amazon Aurora MySQL and Amazon RDS for MySQL](https://aws-oss.beachgeek.co.uk/4dy) - focuses on implementing a cost-effective custom row level security (RLS) solution using native MySQL features, making it suitable for a wide range of use cases without requiring additional software dependencies [hands on]

![Overview of RLS implementation](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2025/06/09/DBBLOG-4695-Implementation-Overview.png)

* [Using the PostgreSQL extension tds_fdw to validate data migration from SQL Server to Amazon Aurora PostgreSQL](https://aws-oss.beachgeek.co.uk/4e5) - presents alternatives you can use for data validation when dealing with tables that lack primary keys, specifically looking at how to use the PostgreSQL tds_fdw extension [hands on]
* [Building a job search engine with PostgreSQL’s advanced search features](https://aws-oss.beachgeek.co.uk/4f7) - helps you understand how to use PostgreSQL’s search features to build an effective job search engine [hands on]

**Other posts to check out**

* [Upgrading your AWS SDK for Go from V1 to V2 with Amazon Q Developer](https://aws-oss.beachgeek.co.uk/4dv) - explores step-by-step how to leverage the power of Amazon Q Developer, to accelerate the migration process and reduce the technical debt associated with the legacy SDK [hands on]

* [Networking of Amazon MQ for RabbitMQ event source mapping for AWS Lambda](https://aws-oss.beachgeek.co.uk/4dr) - dives deep into the relationship between AWS Lambda event source mapping and RabbitMQ networking configurations, exploring various deployment scenarios, from public brokers to isolated subnets, each presenting unique considerations for secure and effective implementation [hands on]

* [Offline caching with AWS Amplify, Tanstack, AppSync and MongoDB Atlas](https://aws-oss.beachgeek.co.uk/4dp) - guides you in how to create an offline-first application with optimistic UI using AWS Amplify, AWS AppSync, and MongoDB Atlas [hands on]

* [Amazon Linux 2023 achieves FIPS 140-3 validation](https://aws-oss.beachgeek.co.uk/4ds) - shares details that Amazon Linux 2023 (AL2023) has achieved Federal Information Processing Standards (FIPS) 140-3 Level 1 validation of our cryptographic modules

* [Announcing the Amazon DCV Access Console as Open Source](https://aws-oss.beachgeek.co.uk/4dt) -  is the announcement that the Amazon DCV Access Console is now available as open source, which I have recently started using and [blogged about here](https://dev.to/aws/configuring-dcv-to-access-ubuntu-desktop-on-ec2-with-a-browser-15i5)

* [Building AI-Ready Applications with Amazon Bedrock and .NET Aspire](https://aws-oss.beachgeek.co.uk/4du) - walks you through how you can integrate AWS Services such as Amazon Bedrock and OpenSearch with .NET Aspire [hands on]
* [Implement semantic video search using open source large vision models on Amazon SageMaker and Amazon OpenSearch Serverless](https://aws-oss.beachgeek.co.uk/4e6) - demonstrates how to use large vision models (LVMs) for semantic video search using natural language and image queries [hands on]

![solution overview](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2025/05/07/ML-14528-fig1.png)

* [Port your .NET Framework applications to Linux with AWS Transform for .NET](https://aws-oss.beachgeek.co.uk/4dx) - teaches you how to port a .NET Framework web application to .NET 8 using AWS Transform for .NET [hands on]
* [AWS Tools for PowerShell V5 now Generally Available](https://aws-oss.beachgeek.co.uk/4fa) - a quick post providing updates on the latest AWS Tools for Powershell, including link to the GitHub repo [hands on]

* [Optimizing Queries with Amazon Managed Prometheus](https://aws-oss.beachgeek.co.uk/4f9) - looks at query governance controls in Amazon Managed Service for Prometheus to optimize their PromQL querying patterns and costs [hands on]

### Quick updates

**AWS CDK**

Announced at the beginning of the month was news of the general availability of the AWS CDK Toolkit Library, a Node.js library that provides programmatic access to core AWS CDK functionalities such as synthesis, deployment, and destruction of stacks. This library enables developers to integrate CDK operations directly into their applications, custom CLIs, and automation workflows, offering greater flexibility and control over infrastructure management. Prior to this release, interacting with CDK required using the CDK CLI, which could present challenges when integrating CDK actions into automated workflows or custom tools. With the CDK Toolkit Library, developers can now build custom CLIs, integrate CDK actions in their existing CI/CD workflows, programmatically enforce guardrails and policies, and manage ephemeral environments.

**Kubernetes**

We have a bunch of quick updates this month.

Kubernetes version 1.33 introduced several new features and bug fixes, and AWS is excited to announce that you can now use Amazon Elastic Kubernetes Service (EKS) and Amazon EKS Distro to run Kubernetes version 1.33. Starting today, you can create new EKS clusters using version 1.33 and upgrade existing clusters to version 1.33 using the EKS console, the eksctl command line interface, or through an infrastructure-as-code tool. Kubernetes version 1.33 includes stable support for sidecar containers, topology-aware routing and traffic distribution, and consideration of taints and tolerations when calculating pod topology spread constraints, ensuring that pods are distributed across different topologies according to their specified tolerance. This release also adds support for user namespaces within Linux pods, dynamic resource allocation for network interfaces, and in-place resource resizing for vertical scaling of pods. To learn more about the changes in Kubernetes version 1.33, see [our documentation](https://docs.aws.amazon.com/eks/latest/userguide/kubernetes-versions-standard.html?trk=fd6bb27a-13b0-4286-8269-c7b1cfaa29f0&sc_channel=el) and the Kubernetes [project release notes](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG/CHANGELOG-1.33.md).

Amazon EKS Pod Identity now provides a simplified experience for configuring application permissions to access AWS resources in separate accounts. With enhancements to EKS Pod Identity APIs, you can now seamlessly configure access to resources across AWS accounts by providing the resource account’s IAM details during the creation of the Pod Identity association. Your applications running in the EKS cluster automatically receive the required AWS credentials during runtime without requiring any code changes. EKS Pod Identity enables applications in your EKS cluster to access AWS resources across accounts through a process called IAM role chaining. When creating a Pod Identity association, you can provide two IAM roles — an EKS Pod Identity role in the same account as your EKS cluster and a target IAM role from the account containing your AWS resources (like S3 buckets or DynamoDB tables). When your application pod needs to access AWS resources, it requests credentials from the EKS Pod Identity, which automatically assumes the roles through IAM role chaining to provide your pod with the necessary cross-account temporary credentials.

Dive deeper into this by checking out the blog post, [Amazon EKS Pod Identity streamlines cross account access](https://aws-oss.beachgeek.co.uk/4e2)

AWS also announced this month the general availability of Private CA Connector for Kubernetes Amazon EKS add-on. This new integration allows customers to easily issue certificates from AWS Private Certificate Authority (AWS Private CA) to their Kubernetes clusters running on Amazon Elastic Kubernetes Service (Amazon EKS). The add-on installs and manages the Private CA Connector for Kubernetes. The connector enables customers to use AWS Private CA certificates for Transport Layer Security (TLS) termination at load balancers, Kubernetes ingress controllers, and pods, as well as securing pod-to-pod communication. With the new Amazon EKS add-on, customers can quickly and easily set up new and existing clusters using automation to leverage AWS Private CA certificates, enhancing security and simplifying certificate management. Previously, this process could take hours or even days and involved numerous manual steps. The connector works in conjunction with cert-manager, an open-source certificate lifecycle management Kubernetes add-on, to provide a comprehensive solution for certificate issuance and management within Kubernetes environments. cert-manager is also available through the Amazon EKS add-ons catalog. Amazon EKS add-ons are curated extensions that automate the installation, configuration, and lifecycle management of operational software for Kubernetes clusters, simplifying the process of maintaining cluster functionality and security. AWS Private CA is a managed service that lets you create private certificate authority hierarchies to issue private certificates. AWS Private CA secures private key material using Federal Information Processing Standard (FIPS) 140-3 Security Level 3 hardware security modules (HSMs).

Also announced this month was the general availability of configuration insights for Amazon EKS Hybrid Nodes. These new insights surface configuration issues impacting the functionality of Amazon EKS clusters with hybrid nodes, and provide actionable guidance on how to remediate identified misconfigurations. Configuration insights are available through the Amazon EKS cluster insights APIs and on the observability dashboard in the Amazon EKS console. Amazon EKS cluster insights now automatically scans Amazon EKS clusters with hybrid nodes to identify configuration issues impairing Kubernetes control plane-to-webhook communication, kubectl commands like exec and logs, and more. Configuration insights surface issues and provide remediation recommendations, accelerating the time to a fully functioning hybrid nodes setup.

**Apache Airflow**

Amazon MWAA is a managed service for Apache Airflow that lets you use the same familiar Apache Airflow platform as you do today to orchestrate your workflows and enjoy improved scalability, availability, and security without the operational burden of having to manage the underlying infrastructure. Amazon MWAA now allows you to update your environment without disrupting your ongoing workflow tasks. By choosing this option, you are now able to update an MWAA environment in graceful manner where MWAA will replace Airflow Scheduler and Webserver components, provision new workers, and wait for ongoing worker tasks to complete before removing older workers. The graceful option is available only for supported Apache Airflow versions (v2.4.3 or later) on MWAA.

**Apache Flink**

Amazon Managed Service for Apache Flink (an open source framework and engine for processing data streams) now supports dual-stack endpoints for both IPv4 and IPv6 traffic. When you make a request to a dual-stack endpoint, the endpoint URL resolves to an IPv6 or an IPv4 address. You can access dual-stack endpoints using the SDK, a configuration file, or an environment variable. The continued growth of the internet is exhausting available Internet Protocol version 4 (IPv4) addresses. IPv6 increases the number of available addresses by several orders of magnitude so customers will no longer need to manage overlapping address spaces in their VPCs.

**Amazon EMR**

Amazon EMR on EKS now supports Service Quotas, improving visibility and control over EMR on EKS quotas. Previously, to request an increase for EMR on EKS quotas, such as maximum number of StartJobRun API calls per second, customers had to open a support ticket and wait for the support team to process the increase. Now, customers can view and manage their EMR on EKS quota limits directly in the Service Quotas console. This enables automated limit increase approvals for eligible requests, improving response times and reducing the number of support tickets. Customers can also set up Amazon CloudWatch alarms to get automatically notified when their usage reaches a certain percentage of a maximum quota.

**Valkey**

General Language Independent Driver for the Enterprise (GLIDE) 2.0, the latest release of one of its official open source Valkey client libraries, in now officially generally available (GA). Valkey is the most permissive open source alternative to Redis stewarded by the Linux Foundation, which means it will always be open source. Valkey GLIDE is a reliable, high-performance, multi-language client that supports all Valkey commands. GLIDE 2.0 brings new capabilities that expand developer support, improve observability, and optimize performance for high-throughput workloads.

Valkey GLIDE 2.0 extends its multi-language support to Go (contributed by Google), joining Java, Python, and Node.js to provide a consistent, fully compatible API experience across all four languages—with more on the way. With this release, Valkey GLIDE now supports OpenTelemetry, an open source, vendor-neutral framework enabling developers to generate, collect, and export telemetry data and critical client-side performance insights. Additionally, GLIDE 2.0 introduces batching capabilities, reducing network overhead and latency for high-frequency use cases by allowing multiple commands to be grouped and executed as a single operation.

**PostgreSQL**

This month AWS announced the open sourcing of pgactive, a PostgreSQL extension for active-active replication. pgactive lets you use asynchronous active-active replication for streaming data between database instances to provide additional resiliency and flexibility in moving data between database instances, including writers located in different regions. This helps maintain availability for operations like switching write traffic to a different instance. pgactive builds on the foundation PostgreSQL logical replication features, such as bidirectional replication between tables starting in PostgreSQL 16, adding capabilities that simplify managing active-active replication scenarios. Open sourcing the pgactive extension allows for more collaboration on developing active-active capabilities of PostgreSQL, while offering features that simplify using PostgreSQL in scenarios that benefit from multiple active instances.

In more PostgreSQL updates, Amazon RDS for PostgreSQL introduces Extended Support minor versions 11.22-rds.20250508 and 12.22-rds.20250508, which include important security updates and bug fixes for PostgreSQL databases.. We recommend upgrading your RDS instances to these latest versions to maintain optimal security and performance of your PostgreSQL deployments. Amazon RDS Extended Support provides you more time, up to three years, to upgrade to a new major version to help you meet your business requirements. During Extended Support, Amazon RDS will provide critical security and bug fixes for your RDS for PostgreSQL databases after the community ends support for a major version. You can run your PostgreSQL databases on Amazon RDS with Extended Support for up to three years beyond a major version’s end of standard support date.

**MariaDB**

Amazon Relational Database Service (Amazon RDS) for MariaDB now supports new community MariaDB minor versions 10.11.13 and 11.4.7. We recommend that you upgrade to the latest minor versions to fix known security vulnerabilities in prior versions of MariaDB, and to benefit from the bug fixes, performance improvements, and new functionality added by the MariaDB community. You can leverage automatic minor version upgrades to automatically upgrade your databases to more recent minor versions during scheduled maintenance windows. You can also leverage Amazon RDS Managed Blue/Green deployments for safer, simpler, and faster updates to your MariaDB instances.

**MySQL**

Amazon RDS for MySQL now supports community MySQL Innovation Release 9.3 in the Amazon RDS Database Preview Environment, allowing you to evaluate the latest Innovation Release on Amazon RDS for MySQL. You can deploy MySQL 9.3 in the Amazon RDS Database Preview Environment which provides the benefits of a fully managed database, making it simpler to set up, operate, and monitor databases. MySQL 9.3 is the latest Innovation Release from the MySQL community. MySQL Innovation releases include bug fixes, security patches, as well as new features. MySQL Innovation releases are supported by the community until the next innovation minor, whereas MySQL Long Term Support (LTS) Releases, such as MySQL 8.0 and MySQL 8.4, are supported by the community for up to eight years.

**Apache Kafka**

First up is news that Amazon Managed Streaming for Apache Kafka (Amazon MSK) now supports Apache Kafka version 3.8 on Express Brokers, introducing new features, bug fixes, and performance improvements for Kafka workloads running on Express Brokers. The update brings enhancements in data compression capabilities. You can now configure compression levels for lz4, zstd, and gzip formats, allowing precise control over the balance between compression efficiency and resource usage.

In related news, AWS Lambda now provides native support for Avro and Protobuf formatted Kafka events with Apache Kafka’s event-source-mapping (ESM), and integrates with AWS Glue Schema registry (GSR), Confluent Cloud Schema registry (CCSR), and self-managed Confluent Schema registry (SCSR) for schema management. This enables you to validate your schema, filter events, and process events using open-source Kafka consumer interfaces. Additionally, customers can use Powertools for AWS Lambda to process their Kafka events without writing custom deserialisation code, making it easier to build their Kafka applications with AWS Lambda. Kafka customers use Avro and Protobuf formats for efficient data storage, fast serialisation and deserialisation, schema evolution support, and interoperability between different programming languages. They utilise schema registry to manage, evolve, and validate schemas before data enters processing pipelines. Previously, customers were required to write custom code within their Lambda function, in order to validate, de-serialise, and filter events when using these data formats. With today's launch, Lambda natively supports Avro and Protobuf as well as integration with GSR, CCSR and SCSR, enabling customers to process their Kafka events using these data formats, without writing custom code. Additionally, customers can optimise costs through event filtering to prevent unnecessary function invocations.

**Mountpoint for Amazon S3**

Mountpoint for Amazon S3 is a simple, open source, high-throughput file client for mounting an Amazon S3 bucket as a local file system. Mountpoint for Amazon S3 now lets you automatically mount an S3 bucket when your Amazon EC2 instance starts up. This simplifies how you define a consistent mounting configuration that automatically applies when your instance starts up and persists the mount when the instance reboots. Previously, to use Mountpoint for Amazon S3, you had to manually mount an S3 bucket after every boot and validate the correct mount options. Now, with support for automatic bucket mounting, you can add your Mountpoint configuration to the fstab file so it is automatically applied every time your instance starts up. Linux system administrators commonly use fstab to manage mount configurations centrally. It contains information about all the available mounts on your compute instance. Once you modify the fstab file to add a new entry for Mountpoint for Amazon S3, your EC2 instance will read the configuration to automatically mount the S3 bucket whenever it restarts.

**OpenZFS**

You can now attach Amazon Simple Storage Service (Amazon S3) Access Points to your Amazon FSx for OpenZFS file systems so that you can access your file data as if it were in S3. With this new capability, your file data in FSx for OpenZFS is accessible for use with the broad range of artificial intelligence, machine learning, and analytics services and applications that work with S3 while your file data continues to reside on the FSx for OpenZFS file system.

An S3 Access Point is an endpoint that helps control and simplify how different applications or users can access data. S3 Access Points now work with FSx for OpenZFS so that applications and services can access file data in FSx for OpenZFS using the S3 API and as if the data were in S3. You can discover new insights, innovate faster, and make even better data-driven decisions with your data in FSx for OpenZFS. For example, you can use your file data to augment generative AI applications with Amazon Bedrock, train machine learning models with Amazon SageMaker, run analyses using Amazon Glue, a wide range of AWS Data and Analytics Competency Partner solutions, and S3-based cloud-native applications.

You can find out more by reading the post, [Amazon FSx for OpenZFS now supports Amazon S3 access without any data movement](https://aws-oss.beachgeek.co.uk/4f6)

**Powertools for AWS Lambda**

Powertools for AWS Lambda now offers a new Amazon Bedrock Agents Function utility that simplifies building serverless applications integrated with Amazon Bedrock Agents. This utility enables developers to easily create AWS Lambda functions that can respond to Amazon Bedrock Agent action requests with built-in parameter injection, response formatting, eliminating boilerplate code and accelerating development.

With the Amazon Bedrock Agents function utility, developers can focus on business logic while the utility handles the complex integration patterns between AWS Lambda and Amazon Bedrock Agents. The utility provides seamless integration with other Powertools features like Logger, Metrics, among other utilities, making it easier to build, test, and deploy production-ready AI applications. This integration significantly improves developer experience when building agent-based solutions that require Lambda functions to process actions requested by Bedrock Agents.

**Red Hat Enterprise Linux**

Red Hat Enterprise Linux (RHEL) for AWS, starting with RHEL 10, is now generally available, combining Red Hat’s enterprise-grade Linux software with native AWS integration. RHEL for AWS is built to achieve optimum performance of RHEL running on AWS. This offering features pre-tuned images with AWS-specific performance profiles, built-in Amazon CloudWatch telemetry, integrated AWS Command Line Interface (CLI), image mode using container-native tooling, enhanced security from boot to runtime, and optimised networking with Elastic Network Adapter (ENA) support.

### Videos of the month

**Meet MCP Servers | Context-Aware AI for Amazon EKS and ECS**

These projects featured in the last newsletter, so it was good that the Containers from the Couch crew decided to put together a nice walk through of how to get started.

{{< youtube qp_Hdv25R2w >}}

---

With re:Inforce just finished, it was good to see that the team had uploaded some of the session videos. Here are a few that caught my eye.

**Create memory safe applications using open source verification tools (APS442)**

Memory-safety errors pose a significant security risk, enabling various attack vectors. This video presents two efforts to reduce memory-safety errors in Rust and C code. Both efforts involve developing verification tools for Rust and C code to check memory safety at scale that you can use too. Our first effort verifies the Rust standard library, a core software used by millions of developers. Our second effort uses a C model checker to verify C code for safety and correctness.

{{< youtube fqhFAdv3XoM >}}

**The AI advantage in AWS CSPM (GRC224)**

Featured many times in this newsletter, Prowler's CEO Toni de la Fuente debuted Prowler’s AI‑powered features - designed to predict misconfigurations, unify compliance workflows, and prescribe fixes in real time. If you’re ready to break free from reactive scans and architect continuous, predictive hardening on AWS, then check this out.

{{< youtube iWUua6P-4qw >}}

**Encrypting data in transit for your Kubernetes applications (DAP341)**

Modern Kubernetes applications require robust encryption for securing data between containers and external clients. In this video, Divyanash Gupta and Ram Ramani from AWS show you how to implement comprehensive end-to-end encryption in transit for Kubernetes applications using AWS Private Certificate Authority and open-source tools. 

{{< youtube iCiDjMBLX8w >}}

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes:  Nicola Cremaschini, Ran Isenberg, Rodrigue Koffi, Ganesh Sambandan, Jay Joshi, Vinod Kisanagaram, Ezat Karimi, Sébastien Stormacq, Gabriel Koo, Dakota Lewallen, szymon-szym, Olivier Lemaitre, David Kerber, Cory Hall, Matthew Bonig, Didier Durand, Ryan Cormack,  Hafiz Syed Ashir Hassan,  Pratik Patel, Amar Surjit, Priyanka Chaudhary, Matteo Luigi Restelli, Dan Kiuna, Igor Alekseev, Anuj Panchal, Melody Yang, Dai Ozaki, Noritaka Sekiyama, Amir Shenavandeh, Xi Yang, Rafal Pawlaszek, Witold Kowalik, Mahak Arora, Andrew Morgan, Mayank Kumar, Gamal Gayle, Janya Ram, Prem Nambi, Chris Procunier, Jay Ramachandran, Trevor Schiavone, Neeraj Handa, Artur Rodrigues, Juveria Kanodia, Mark Fawaz, Sukanth Rajan, Kiranmayee Mulupuru, Spencer Erickson, Liana Hadarean, Ryan Coleman, Aneesh Chandra PN, Aritra Gupta, Ananta Khanal, Madhu Nagaraj, Ashok Srirama, George John, Nikos Tragaras, Raphaël Afanyan, Lorenzo Nicora, Simone Pomata, Subham Rakshit, Amit Arora, Vanshika Nigam, Alexander Arzhanov, Ivan Sosnovik, Nikita Bubentsov, Aarthi Srinivasan, Dhananjay Badaya, Praveen Kumar, Carlos Santana, Sriram Ranganathan, Sabari Sawant, Frank Carta, Sri Potluri, Suvojit Dasgupta, Anurag Srivastava, Chandan Rupakheti, Sriharsh Adari, Venu Thangalapally, Shubham Purwar, Nitin Kumar, Prashanthi Chinthala, Eran Balan, Ben Fields, Yann Richard, Suthan Phillips, Binaya Sharma, Trevor Roberts Jr, Ige Adetokunbo Temitayo, Damien Jones, Joris Conijn, Kenta Goto, Rehan van der Merwe, Arjun kumar Giri, Jiaping Zeng, Dave Bechberger, Agam, Jagdeep Singh Soni, Todd Sharp, Gary Stafford, Veliswa Boya, Laura Salinas, Maandeep Singh, Jose Romero and Priya Tiruthani.


### Stay in touch with open source at AWS

Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) for more open source goodness.

One of the pieces of feedback I received was to create a repo where all the projects featured in this newsletter are listed. Where I can hear you all ask? Well as you ask so nicely, you can meander over to[ newsletter-oss-projects](https://aws-oss.beachgeek.co.uk/3l8).

Made with ♥ from DevRel