---
title: 'AWS open source newsletter #214'
date: '2025-09-29'
tags : [ oss-newsletter, aws open source,  Firecracker, Kubernetes, Amazon EKS, Strands Agents, FreeBSD, aws-nuke, CrewAI, LangGraph, Karpenter,  Prometheus, Grafana, Kubecost, MLflow, Apache Flink, Apache. Airflow, MWAA, Apache Iceberg, Apache Spark, MySQL, PostgreSQL, Amazon EMR,  Apache YuniKorn, AWS CDK, Valkey, InfluxDB, Amazon Linux, Amazon Corretto, LocalStack, OpenSearch, RabbitMQ, AWS Neuron SDK]
canonicalUrl: "https://dev.to/aws/aws-open-source-newsletter-214-ekm"
---

##  Edition #214- September 2025

Welcome to issue #214 of the AWS open source newsletter, the newsletter where I try and provide you the best open source on AWS content. Sometimes less is more, and I am using that as an excuse as I was on holiday for the first two weeks of September (in lovely Cornwall for those wondering, hiking the SW Coastal Path), and so have less time that usual to put this together. That said, this edition is still packed with great new projects to check out, and all the other usual goodness. In this edition, we have a nice selection of projects that broad range of use cases - some great developer tool extensions and integrations for generative AI, tools to help you optimise the developer experience when developing solutions using AgentCore, some nice tools to help you work with Amazon ECS and EC2, and much more.

 The projects will keep you busy until next month for sure, but we also have plenty of reading material in this months newsletter. In this edition we have featured projects that include Firecracker, Kubernetes, Strands Agents, FreeBSD, aws-nuke, CrewAI, LangGraph, Karpenter,  Prometheus, Grafana, Kubecost, MLflow, Apache Flink, Apache. Airflow, Apache Iceberg, Apache Spark, MySQL, PostgreSQL, Amazon EMR,  Apache YuniKorn, AWS CDK, Valkey, InfluxDB, Amazon Linux, Amazon Corretto, LocalStack, OpenSearch, RabbitMQ, AWS Neuron SDK . That should keep you all very busy!

Check out the list of contributors at the end of the newsletter, and as always, get in touch if you want me to feature your projects in this open source newsletter. 

**Make sure you check out**

Check out [General Availability Release of the Migration Tool for the AWS SDK for Java 2.x](https://aws-oss.beachgeek.co.uk/4jd) if you have been using the older Java AWS SDK's - this post from David Ho came out just before publishing, and looks at a migration tool to help you update any applications you have using the older SDK's.

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution. The projects mentioned here do not represent any formal recommendation or endorsement, I am just sharing for greater awareness as I think they look useful and interesting!*

### Tools

**nova-act-extension**

[nova-act-extension](https://aws-oss.beachgeek.co.uk/4j0) is a very nice VSCode extension (Kiro, Cursor, VSCode) that provides a number of new commands that helps you tap into the power of [Amazon Nova Act](https://github.com/aws/nova-act), an early research preview of an SDK + model for building agents designed to reliably take actions in web browsers. The README covers some of the use cases that are supported and that you can try out with this plugin. If you have not looked at these tools yet, its worth just experimenting to get a feel of how they work and to start thinking about what use cases you might be able to come up with.

![demo of nova-act extension ](https://github.com/aws/nova-act-extension/blob/main/resources/walkthrough/step2_chat.gif?raw=true)

My good friend **Donnie Prakoso** has also put together a nice blog post which you can read, [Accelerate AI agent development with the Nova Act IDE extension](https://aws-oss.beachgeek.co.uk/4jb) which does a great job of walking you through some examples of how you might want to use this extension.

**amazonq.nvim**

[amazonq.nvim](https://aws-oss.beachgeek.co.uk/4j1) is perfect for neovim users, and allows you to integrate Amazon Q Developer, providing Chat functionality, Inline Code Suggestions, and other Amazon Q Developer capabilities. After installation, authenticate through IAM Identity Center or AWS Builder ID. You can use Amazon Q for free without an AWS account by authenticating with Builder ID. The README has lots of glorious configuration details that will allow you to customise and control how this works (which is after all half the fun of using tools like neovim)

**pyssm-client**

[pyssm-client](https://aws-oss.beachgeek.co.uk/4j2) is another project from **Damon Cortesi**, who will be no stranger to regular readers of this newsletter. What has Damon been cooking up this time? Well, to answer this, he has create a tool that provides an enhanced Python AWS SSM Session Manager client with interactive sessions, exec, and file transfer support. It speaks the same binary protocol as the official Go plugin and provides additional functionality like library imports and extended CLI commands. Check out the README for more highlights of why you should check this out. If you do any amount of work connecting to EC2 instances, you will find this useful.

**ttok4bedrock**

[ttok4bedrock](https://aws-oss.beachgeek.co.uk/4j3) is a very helpful tool from my colleague **Danillo Poccia** that helps developers understand token consumption when working with large language models through Amazon Bedrock. This is important as it can help manage costs and help you to stay within model limits. While the Bedrock console provides token counts after each API call, developers need a way to measure tokens before sending requests, especially when building applications that process large volumes of text or require precise truncation. Danilo has put together a post that walks you through how to use this tool, so go read it - [Token Counting Meets Amazon Bedrock](https://dev.to/aws/token-counting-meets-amazon-bedrock-4dk5)

**agentcore-memory-browser**

[agentcore-memory-browser](https://aws-oss.beachgeek.co.uk/4j4) is another project from  **Danillo Poccia** (he is on fire at the moment!!)   that provides a web interface for browsing and exploring Amazon Bedrock AgentCore Memory resources. This application provides a user friendly way to interact with AgentCore Memory data through both control plane and data plane APIs. Check out the README for a short video of what this looks like and how it works - it is really very cool.

As always, he has also put together a supporting blog post, [Visualizing AI Agent Memory: Building a Web Browser for Amazon Bedrock AgentCore Memory](https://dev.to/aws/visualizing-ai-agent-memory-building-a-web-browser-for-amazon-bedrock-agentcore-memory-3571)

**lazy-ecs**

[lazy-ecs](https://aws-oss.beachgeek.co.uk/4j5) is a tool from **Janne Sinivirta** that provides a new CLI tool for working with Amazon ECS, and specifically for navigating Amazon ECS Clusters. Check out the README to find out what you can do with this, and in the meantime I will leave you with a screenshot.

![demo screen of lazy-ecs](https://github.com/vertti/lazy-ecs/blob/main/images/lazy-ecs-demo.jpg?raw=true)

**skopeo**

[skopeo](https://aws-oss.beachgeek.co.uk/4j7) is a super handy tool for those folks spending a lot of time managing container images. skopeo is a command line utility that performs various operations on container images and image repositories. It does not require root privileges for most of the operations (fantastic) and has lots of capabilities so dive into the README. I found out about this tool by reading **AWS Community Builder Todor Todorov's** post, [How to Migrate ECR Docker Images Between Repositories (with Automation)](https://dev.to/aws-builders/how-to-migrate-ecr-docker-images-between-repositories-with-automation-441h) where he shares some of the ways he is using this tool. Great stuff.

### Demos, Samples, Solutions and Workshops

**agentcore-multi-framework-examples**

[agentcore-multi-framework-examples](https://aws-oss.beachgeek.co.uk/4j6) - yet more goodness from **Danillo Poccia** that contains sample implementations of AI agents using different frameworks (Strands, CrewAI, Pydantic AI, LlamaIndex, LangGraph, and MemoryMCP), all integrated with Amazon Bedrock AgentCore for production deployment and centralised memory management. Essential viewing.

**postgres-rust-migration**

[postgres-rust-migration](https://aws-oss.beachgeek.co.uk/4j8) is a sample repo from **AWS Community Builder Vivek V** that demos how Kiro can be used to migrate large codebases and working with such repos using Kiro spec-driven development approach. From the README, it is "a comprehensive migration of the PostgreSQL database management system from C to Rust, leveraging Rust's memory safety guarantees, performance characteristics, and modern language features while maintaining 100% compatibility with existing PostgreSQL functionality, protocols, and ecosystem.". The repo also provides a link to a video, and you can also read his post on this top, [Taming Large Codebases with Kiro: Lessons from a 58K-LoC Rust Migration](https://dev.to/kirodotdev/taming-large-codebases-with-kiro-lessons-from-a-58k-loc-rust-migration-36p9)

**openvpn-sftp**

[openvpn-sftp](https://aws-oss.beachgeek.co.uk/4ja) is a repo I found whilst I was spending my daily perusing time of the /aws subreddit. It provides a repo that provides sample code to help you automate and optimise the setting up of openvpn on AWS. From the author (I presume) themselves:

> "I have created my first nice (imo) terraform for setting up an openvpn community container with a secure sfptgo instance behind it. This is great for anyone that wants their own vpn setup without connection limits. So now you can easily deploy your own secure network and file share solution. Sftp go handles webdav and even smb if you want. This solution does not yet handle Route 53 or any other DNS option nor does it handle persisting the SFTPGo certs that are generated on container start. That stuff is coming but this setup is still fully usable as is with static IPs. This should be particularly interesting for the AWS crowd as it makes it super easy to setup a scalable custom managed VPN without enterprise pricing constraints."

As always with these kinds of repos, make sure you don't blindly trust and review and check out what is configured to make sure you are satisfied with what its doing.

**event-resources-website**

[event-resources-website](https://aws-oss.beachgeek.co.uk/4j9) is a very handy project for those of you running any kind of event, that lets you build a customisable static website on Amazon S3 and Amazon CloudFront to share event resources with attendees. Perfect for speakers who want to share account creation links, surveys, demo repositories, and social media links after presentations. Eli has also put together a supporting blog post on how she put this together, so go read Building an [Event Resources Website with AWS CDK and Amazon Q Developer CLI](https://dev.to/aws/building-an-event-resources-website-with-aws-cdk-and-amazon-q-developer-cli-5do2)

### AWS and Community blog posts

**This weeks essential reading**

Here are the posts that I think are essential reads, so start here. We have more than we usually do, but thought these were all essential reads this month.

* [Seven Years of Firecracker](https://aws-oss.beachgeek.co.uk/4iy) - a look back at some of the new ways that AWS is using Firecracker under the hood (no spoilers, but the post does a lovely job of diving deep into this) and this post is an essential read
* [Strands Agents and the Model-Driven Approach](https://aws-oss.beachgeek.co.uk/4i9) - looks at how the Strands Agents SDK embraces a model driven approach that eliminates the brittleness of traditional agent frameworks by letting modern large language models drive their own behaviour, make intelligent decisions about tool usage, and adapt dynamically to any scenario, resulting in more resilient and flexible agents [hands on]
* [Multi Agent Collaboration with Strands](https://aws-oss.beachgeek.co.uk/4jc) - introduces and dives deep into  a new agentic AI pattern for orchestrating multi agents, the arbiter [hands on]

![the agentic ai arbiter pattern](https://d2908q01vomqb2.cloudfront.net/7719a1c782a1ba91c031a682a0a2f8658209adbf/2025/09/09/Screenshot-2025-09-09-at-9.42.32%E2%80%AFam-1024x808.png)

* [Use Raspberry Pi 5 as Amazon EKS Hybrid Nodes for edge workloads](https://aws-oss.beachgeek.co.uk/4ia) - demonstrates how to use the Raspberry Pi 5 as an Amazon EKS Hybrid Node to run edge workloads, enabling seamless integration of cloud and on-premises infrastructure while addressing latency and reliability requirements for real-time data processing - love it!! [hands on]

![obligatory network architecture diagram!](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2025/09/15/Screenshot-2025-09-15-at-16.14.10.png)

**Community**

Each month I spend time reading posts from across the AWS community on open source topics. In this section I share what personally caught my eye and interest, and I hope that many of you will also find them interesting. I didn't have that much free time this month, so this section is a bit "light" this month, so apologies if I missed something (but please let me know so I can include it next month!)

First up is a post I missed when it was published (so apologies), shared by **AWS Hero Colin Percival** that takes a look at all the great work he has done helping to make sure that you have a good experience running FreeBSD on AWS in his post, [A year of funded FreeBSD](https://aws-oss.beachgeek.co.uk/4iz). Really great read, so thanks for sharing that Colin.  From FreeBSD we move onto AWS CDK, and **AWS Hero Thorsten Hoeger** who has put together [CDK Environment Management: Static vs Dynamic Stack Creation](https://dev.to/aws-heroes/cdk-environment-management-static-vs-dynamic-stack-creation-383l) where he walks you through your options when considering how to choose the right environment strategy for your CDK stacks. Nice post, which is great if you are new to AWS CDK and want to understand some of the options available, with their trade offs.

Moving to Strands Agents, an open source framework that makes it super easy to build very powerful generative AI applications, comes [Amazon Strands Agents: The Model-First Revolution in AI Agent Development](https://chetanhirapara.medium.com/amazon-strands-agents-the-model-first-revolution-in-ai-agent-development-7a488b8a78e1) from **Chetan Hirapara** who walks you through this, and takes a look at use cases, when to use (and not), as well as comparing it to some other popular open source frameworks that are in this space. Sticking with Strands Agents, my colleague **Danillo Poccia** has been spending a lot of time getting to know Strands Agents, and this month he released a number of must read posts, so want to list these here as they are all worth reading (bravissimo). Start off with [Building Production-Ready AI Agents with Strands Agents and Amazon Bedrock AgentCore](https://dev.to/aws/building-production-ready-ai-agents-with-strands-agents-and-amazon-bedrock-agentcore-3dg0), then follow that with main of [Building Production-Ready AI Agents with CrewAI and Amazon Bedrock AgentCore](https://dev.to/aws/building-production-ready-ai-agents-with-crewai-and-amazon-bedrock-agentcore-2g36), and it would be rude to skip desert of [Building Production-Ready AI Agents with LangGraph and Amazon Bedrock AgentCore](https://dev.to/aws/building-production-ready-ai-agents-with-langgraph-and-amazon-bedrock-agentcore-4h5k).  As a side note, Danillo has recently branched out into the world of fiction writing. He has created (in my humble opinion) a really first class page turner in his first (of hopefully many) books called [The Marginalia Messenger (The Forgotten Messages)](https://www.amazon.co.uk/Marginalia-Messenger-Forgotten-Messages/dp/B0FJRT8FJ8/ref=sr_1_2?crid=1WDHIO521WYVO&dib=eyJ2IjoiMSJ9.JZR_QqdrTFK4y4jevRritnQRKy6uKRMGreLDzVkJiU8kCCGj133ZptdFNOtO9nAIyoFzFb1pXDR3e_w4D7VDYSQkS-gSit5FRZzRr0N-cnEGCasaCBrvB6V6r5pSg5uKIGTHPp-HGRsjFL5dENCU_oMnZ8oa7E34Ju2mvpndp4dcS8TQyx1wzy49MwZ4VW0qLg7E7cpOBCxUgV63nQ5QbFKckTJ__-biUmi2BcVjysA.tzKyhoj-x9Z8fNFXeJQWUXTvhdW1OF9_tlRqoY2AiCU&dib_tag=se&keywords=marginalia&qid=1758730533&sprefix=marginalia%2Caps%2C101&sr=8-2). I highly recommend this, I thoroughly enjoyed it.

From Strands Agents we move to a project that was featured in [#211](https://dev.to/aws/aws-open-source-newsletter-211-188) of this newsletter, iam-collect. **AWS Community Builder David Kerber** has put together [Fantastic AWS Policies and Where to Find Them](https://dev.to/aws-builders/fantastic-aws-policies-and-where-to-find-them-38f9) that dives into this project so I recommend you check this one out. To finish up this month we have **AWS Community Builder Roman Tsypuk** has put together a post featuring one of my favourite open source projects, aws-nuke, a project that allows you to delete resources easily from AWS Accounts. It should go without saying that you should be **VERY CAREFUL** when using this tool as its very effective. You can read his post, [AWS-nuke controlled resources cleanup in multiple aws accounts](https://dev.to/aws-builders/aws-nuke-controlled-resources-cleanup-in-multiple-aws-accounts-313d) to get more of an idea of how it works (from the safety of your armchair!).

Thats all for this month. If you have an open source article you want to share with the community, drop me a message (LinkedIn, or via [ricsue@amazon.co.uk](mailto:ricsue@amazon.co.uk) and I will be sure to check it out.

**Cloud Native**

* [How to build highly available Kubernetes applications with Amazon EKS Auto Mode](https://aws-oss.beachgeek.co.uk/4iq) - looks at the capabilities of EKS Auto Mode in depth, subjecting it to a series of challenging scenarios such as failure simulations, node recycling, and cluster upgrades—all while maintaining uninterrupted service traffic [hands on]

* [Building Resilient Multi-cluster Applications with Amazon EKS, Part 1: Implementing Cross-cluster Load Balancing with NLB](https://aws-oss.beachgeek.co.uk/4il) - the first in a three part series that explores design patterns and strategies to enhance application resiliency through multi-cluster deployment on Amazon EKS, focusing on implementing cross-cluster load balancing with Network Load Balancer (NLB) to address challenges in maintaining high availability during critical operations like cluster upgrades, add-on updates, and workflow changes [hands on]
* [Implementing granular failover in multi-Region Amazon EKS](https://aws-oss.beachgeek.co.uk/4im) - demonstrates how to configure Amazon Route 53 to enable unique failover behaviour for each application within your multi-tenant Amazon EKS environment across AWS Regions, which allows you to maintain the cost benefits of shared infrastructure while meeting diverse availability requirements [hands on]

* [Kubernetes right-sizing with metrics-driven GitOps automation](https://aws-oss.beachgeek.co.uk/4in) - looks at how achieve Kubernetes right sizing using an automated GitOps driven approach to resource optimisation using AWS services like Amazon Managed Service for Prometheus and Amazon Bedrock [hands on]

![solution overview](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2025/09/04/CONTAINERS-1519-1.jpeg)

* [Dynamic Kubernetes request right sizing with Kubecost](https://aws-oss.beachgeek.co.uk/4ix) - shows you how to use the Kubecost Amazon Elastic Kubernetes Service (Amazon EKS) add-on to lower infrastructure costs and boost Kubernetes efficiency [hands on]

* [How to run AI model inference with GPUs on Amazon EKS Auto Mode](https://aws-oss.beachgeek.co.uk/4iu) - will help you through the steps needed to deploy inference workloads on EKS Auto Mode [hands on]
* [Improve cost visibility of Machine Learning workloads on Amazon EKS with AWS Split Cost Allocation Data](https://aws-oss.beachgeek.co.uk/4ic) - summarises the introduction of split cost allocation support for accelerated workloads in Amazon Elastic Kubernetes Service (EKS), enabling customers to track container level resource costs for accelerator powered workloads, providing a consolidated view of cloud expenditures
* [Use AWS Deep Learning Containers with Amazon SageMaker AI managed MLflow](https://aws-oss.beachgeek.co.uk/4ie) - helps explain how you can use AWS Deep Learning Containers with Amazon SageMaker's AI managed MLflow to enable specialised machine learning environments while providing comprehensive lifecycle management, automatic logging, enhanced comparison capabilities, and complete lineage tracking [hands on]

* [Optimizing metrics ingestion with Amazon Managed Service for Prometheus](https://aws-oss.beachgeek.co.uk/4ij) - part of a series of blogs, in this post they explore how to set up cross-account metrics ingestion and establish governance controls with Amazon Managed Service for Prometheus [hands on]
* [Migrating from API keys to service account tokens in Grafana dashboards using Terraform](https://aws-oss.beachgeek.co.uk/4ik) - dives into how to migrate from using API keys to using service account tokens in Grafana dashboards when automating Amazon Managed Grafana resource management using Terraform, and how to securely store and rotate the tokens using AWS Secrets Manager and AWS Lambda [hands on]

**Data and Analytics**

* [Deep dive into the Amazon Managed Service for Apache Flink application lifecycle ‚Part 1](https://aws-oss.beachgeek.co.uk/4id) - the first of a two part post that provides a deep dive into the Amazon Managed Service for Apache Flink application lifecycle, covering core concepts, application workflow during normal operations, and the potential failures, monitoring, and troubleshooting  [hands on]
* [Achieve full control over your data encryption using customer managed keys in Amazon Managed Service for Apache Flink](https://aws-oss.beachgeek.co.uk/4ir) - looks at how Amazon Managed Service for Apache Flink now supports the use of customer managed keys (CMKs) for encrypting application data, enabling organisations to maintain full control over their encryption keys and meet strict compliance requirements [hands on]

![overview of solution architecture](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2025/08/29/BDB-5441-01-actors.png)

* [Use Apache Airflow workflows to orchestrate data processing on Amazon SageMaker Unified Studio](https://aws-oss.beachgeek.co.uk/4if) - Apache Airflow (Amazon Managed Workflows for Apache Airflow, or MWAA) workflows can be used to orchestrate data processing on Amazon SageMaker Unified Studio, allowing for the development, testing, and running of end-to-end machine learning pipelines that span multiple services and tools [hands on]

* [Unlock the power of Apache Iceberg v3 deletion vectors on Amazon EMR](https://aws-oss.beachgeek.co.uk/4io) - compares and evaluate the performance of the new binary deletion vectors in Iceberg v3 with respect to traditional position delete files of Iceberg v2 using Amazon EMR version 7.10.0 with Apache Spark 3.5.5 [hands on]

* [Dynamic view-based data masking in Amazon RDS and Amazon Aurora MySQL ](https://aws-oss.beachgeek.co.uk/4ig)- looks at how Amazon RDS and Amazon Aurora MySQL offer a solution for dynamic view-based data masking, which allows organisations to safeguard personally identifiable information (PII) and other sensitive data while maintaining its utility for development, testing, and analytics purposes, by leveraging database views to hide or transform sensitive data without modifying the original tables [hands on]
* [Group database tables under AWS Database Migration Service tasks for PostgreSQL source engine](https://aws-oss.beachgeek.co.uk/4is) - explores methods for leveraging system catalogs and statistics views to examine database dimensions, operational load, and hardware configurations that can help you determine the ideal number of tasks and table clusters for effective database migrations [hands on]

* [Deploy Apache YuniKorn batch scheduler for Amazon EMR on EKS](https://aws-oss.beachgeek.co.uk/4iv) - describes how Apache YuniKorn, a custom resource scheduler designed for big data and machine learning workloads on Kubernetes, can be deployed to optimise resource scheduling and improve cluster utilisation, job completion times, and resource allocation for organisations running large-scale Apache Spark workloads on Amazon EMR on EKS [hands on]

![overview of Apache YuniKorn batch schedyler for Amazon EMR on EKS architecture](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2025/08/20/BDB-5168-image-1.png)

* [Streamline Spark application development on Amazon EMR with the Data Solutions Framework on AWS](https://aws-oss.beachgeek.co.uk/4ih) - discusses how to streamline the development process of Apache Spark applications on Amazon EMR using the Data Solutions Framework on AWS, which includes setting up a local development environment, provisioning serverless Spark infrastructure using the AWS Cloud Development Kit (AWS CDK), and implementing a CI/CD pipeline for automated testing and deployment [hands on]

![overview of solution architecture](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2025/09/01/image-7.jpeg)

* [Reduce your Amazon ElastiCache costs by up to 60% with Valkey and CUDOS](https://aws-oss.beachgeek.co.uk/4it) - does a great job at showing you how to save costs on Amazon ElastiCache by upgrading your cluster engine to ElastiCache for Valkey, which can potentially lead to 60% cost savings [hands on]

* [Scale read operations with Amazon Timestream for InfluxDB read replicas](https://aws-oss.beachgeek.co.uk/4iw) - looks at the Timestream for InfluxDB read replica feature, and how this can help you optimise your cluster for high query performance workloads [hands on]

**Other posts to check out**

* [DISA STIG for Amazon Linux 2023 is now available](https://aws-oss.beachgeek.co.uk/4ip) - looks at the Security Technical Implementation Guide (STIG) for Amazon Linux 2023 (AL2023), developed in collaboration with Amazon Web Services and the U.S. Defence Information Systems Agency (DISA), which provides detailed OS security hardening configurations for organisations deploying AL2023 in DOD environments and other agencies requiring DISA STIG alignment [hands on]

* [Switzerland‚ Open Source Apertus LLMs now available on Amazon SageMaker AI](https://aws-oss.beachgeek.co.uk/4ib)  - looks Switzerland's open source Apertus large language models, developed by the Swiss AI Initiative, that are now available on Amazon SageMaker AI, enabling Swiss and European organisations to leverage this AI technology while maintaining data residency needs

### Quick updates

**Amazon Corretto**

Amazon Corretto 25, a Long Term Support (LTS) version, is now generally available. Amazon Corretto is a no-cost, multi-platform, production-ready distribution of OpenJDK. You can download Corretto 25 for Linux, Windows, and macOS from our downloads page.

Amazon Corretto 25 new features include:

* Two features that were initially released as experimental in JDK 24 are now LTS production-ready in JDK 25: **Compact Object Headers**: designed to lower heap memory usage by shrinking object headers from 96-128 bits down to 64 bits, and **Generational Shenandoah GC**: engineered to provide sustainable throughput and lower p99 pause times or similar pause times with a smaller heap and reduced CPU usage.
* Ahead-of-Time (AOT) Caching: designed to improve cold-start and warm-up time by reusing pre-parsed pre-linked classes and compilation profiles between training and production runs.
* Language improvements: primitive types in patterns, flexible constructors, module‑wide imports, compact source files, scoped values for thread-local variables, stable values for immutable data, all designed to cut boilerplate, keep everyday code shorter and safer.
* Observability: JDK Flight Recorder gains CPU‑time sampling, cooperative sampling and method‑trace events for low‑overhead production profiling.
* Structured Concurrency: designed to provide coordinated task management, allowing related tasks fail or finish together.
* Vector API: developed to provide computations that compile to optimal vector instructions on supported CPUs.
* Virtual Thread pinning improvements: reduces thread pinning in synchronized blocks for better scalability.

A detailed description of these features can be found [on the OpenJDK 25 Project page](https://aws-oss.beachgeek.co.uk/4i7). Amazon Corretto 25 is distributed by Amazon under[ an open source license](https://openjdk.org/legal/gplv2+ce.html) and will be supported through October 2032.

**LocalStack**

AWS launched LocalStack integration in Visual Studio Code (VS Code), enabling developers to easily test and debug serverless applications in their local IDE. This integration is now available to developers using the AWS Toolkit for VS Code (v3.74.0 or later). With this new integration, developers can use LocalStack to locally emulate and test their serverless applications using familiar VS Code interface without switching between tools or managing complex setup, thus simplifying their local serverless development process.

LocalStack enables developers to emulate AWS services such as AWS Lambda, Amazon SQS, Amazon API Gateway, and DynamoDB for local application development and testing. Previously, to use LocalStack to emulate AWS services in VS Code, developers had to manually configure ports, make code changes, and switch context between the IDE and LocalStack interface. Now, with LocalStack integration in VS Code, developers can connect to LocalStack environment from their IDE without manual configuration or code changes. This gives developers access to emulated AWS resources in the IDE, making it easy to build and test serverless applications locally. For example, they can now easily test and debug Lambda functions and their interactions with AWS services in a LocalStack emulated environment from their IDE.

I am excited about this new capability, and if you want to find out more, check out Micah Walter's post [Accelerate serverless testing with LocalStack integration in VS Code IDE](https://aws-oss.beachgeek.co.uk/4i8).

**AWS Cloud Development Kit (CDK)**

AWS Cloud Development Kit (CDK) CLI now enables safe infrastructure refactoring through the new 'cdk refactor' command in preview. This feature allows developers to rename constructs, move resources between stacks, and reorganise CDK applications while preserving the state of deployed resources. By leveraging AWS CloudFormation's refactor capabilities with automated mapping computation, CDK Refactor eliminates the risk of unintended resource replacement during code restructuring.

Previously, infrastructure as code maintenance often requires reorganising resources and improving code structure, but these changes traditionally risked replacing existing resources due to logical ID changes. With the CDK Refactor feature, developers can confidently implement architectural improvements like breaking down monolithic stacks, introducing inheritance patterns, or upgrading to higher-level constructs without complex migration procedures or risking downtime of stateful resources. This allows teams to continuously evolve their infrastructure code while maintaining the stability of their production environments.

**OpenSearch**

You can now run OpenSearch version 3.1 in Amazon OpenSearch Service. OpenSearch 3.1 introduces several improvements in areas like search relevance and performance, and introduces features that simplify development of vector-driven applications for generative AI workloads. This launch incorporates Lucene 10 that enables optimised vector field indexing resulting in faster indexing times and reduced index sizes, sparse indexing for CPU and storage efficiency improvements, and vector quantisation to reduce memory usage. Other key areas of improvement include improved range query performance, which benefits log analytics and time-series workloads, and reduced latency for high-cardinality aggregations. This launch also introduces a new Search Relevance Workbench, which provides integrated tools for teams to evaluate and optimise search quality through experimentation. Additionally, this launch includes several improvements in vector search capabilities. First, Z-score normalisation improves hybrid search reliability by reducing the impact of outliers and different score scales. Finally, you can now boost efficiency of searches using memory-optimised search that enables the Faiss engine to operate efficiently by memory-mapping the index file and using the operating system's file cache to serve search requests.

**MySQL**

Amazon RDS for MySQL now supports community MySQL Innovation Release 9.4 in the Amazon RDS Database Preview Environment, allowing you to evaluate the latest Innovation Release on Amazon RDS for MySQL. You can deploy MySQL 9.4 in the Amazon RDS Database Preview Environment which provides the benefits of a fully managed database, making it simpler to set up, operate, and monitor databases. MySQL 9.4 is the latest Innovation Release from the MySQL community. MySQL Innovation releases include bug fixes, security patches, as well as new features. MySQL Innovation releases are supported by the community until the next innovation minor, whereas MySQL Long Term Support (LTS) Releases, such as MySQL 8.0 and MySQL 8.4, are supported by the community for up to eight years. Please refer to the MySQL 9.4 release notes and Amazon RDS MySQL release notes for more details.

> Note! Amazon RDS Database Preview Environment supports both Single-AZ and Multi-AZ deployments on the latest generation of instance classes. Amazon RDS Database Preview Environment database instances are retained for a maximum of 60 days and are automatically deleted after the retention period. Amazon RDS database snapshots created in the Preview Environment can only be used to create or restore database instances within the Preview Environment.

In more MySQL news, Amazon RDS for MySQL now supports new Amazon RDS Extended Support minor version 5.7.44-RDS.20250818. We recommend that you upgrade to this version to fix known security vulnerabilities and bugs in prior versions of MySQL. Learn more about upgrading your database instances, including minor and major version upgrades, in the Amazon RDS User Guide. Amazon RDS Extended Support provides you more time, up to three years, to upgrade to a new major version to help you meet your business requirements. During Extended Support, Amazon RDS will provide critical security and bug fixes for your MySQL databases on Aurora and RDS after the community ends support for a major version. You can run your MySQL databases on Amazon RDS with Extended Support for up to three years beyond a major version’s end of standard support date.

**PostgreSQL**

Amazon RDS for PostgreSQL 18.0 is now available in the Amazon RDS Database Preview Environment, allowing you to evaluate the latest PostgreSQL features while leveraging the benefits of a fully managed database service. This preview environment provides you a sandbox where you can test applications and explore new PostgreSQL 18.0 capabilities before they become generally available. PostgreSQL 18.0 includes "skip scan" support for multicolumn B-tree indexes and improves WHERE clause handling for OR and IN conditions. It introduces parallel Generalised Inverted Index (GIN) builds and updates join operations. It now supports Universally Unique Identifiers Version 7 (UUIDv7), which combines timestamp-based ordering with traditional UUID uniqueness to boost performance in high-throughput distributed systems. Observability improvements show buffer usage counts and index lookups during query execution, along with per-connection I/O utilisation metric. 

> Note! Amazon RDS Database Preview Environment database instances are retained for a maximum period of 60 days and are automatically deleted after the retention period. Amazon RDS database snapshots that are created in the preview environment can only be used to create or restore database instances within the preview environment. You can use the PostgreSQL dump and load functionality to import or export your databases from the preview environment.

**RabbitMQ**

Amazon MQ now supports OAuth 2.0 authentication and authorisation for RabbitMQ brokers with public identity providers in both single instance and highly available Multi-AZ cluster deployments. This feature enables RabbitMQ brokers to authenticate clients and users using JWT-encoded OAuth 2.0 access tokens, providing enhanced security and flexibility in access management. You can configure OAuth 2.0 on your RabbitMQ broker on Amazon MQ using the AWS Console, AWS CloudFormation, AWS Command Line Interface (CLI), or the AWS Cloud Development Kit (CDK). This feature is available in all AWS regions where Amazon MQ is available. To get started, create a new RabbitMQ broker with OAuth 2.0 authentication or update your existing broker's configuration to enable OAuth2.0 support. This feature maintains compatibility with standard RabbitMQ OAuth 2.0 implementations, ensuring seamless migration for existing OAuth 2.0 enabled brokers. 

**AWS Neuron SDK**

AWS announced the general availability of Neuron SDK 2.26.0, delivering improvements for deep learning workloads on AWS Inferentia and Trainium-based instances. This release introduces support for PyTorch 2.8 and JAX 0.6.2, along with enhanced inference capabilities on Trainium2 (Trn2) instances. These updates enable developers to leverage the latest frameworks while benefiting from improved model deployment flexibility and performance optimisations. With Neuron SDK 2.26.0, customers can now deploy FLUX.1-dev image generation model, along with Llama 4 Scout and Maverick variants (beta) on Trn2 instances. The release introduces expert parallelism support (beta) for efficient distribution of Mixture-of-Experts (MoE) models across multiple NeuronCores, and adds new capabilities through new Neuron Kernel Interface (NKI) APIs. The updated Neuron Profiler provides improved capabilities, including system profile grouping for distributed workloads.

### Videos of the month

**Open-Source Multi-Agent Framework (Strands Tutorial)**

**Matthew Berman** walks you through building a multi agent research team that goes out and gets information for external websites in real time, before compiling that information in a report. To do this, he uses Strands Agents.

{{< youtube Z6urONR1b2s >}}

**Amazon EKS Ultra Scale: Running 100K-Node Kubernetes Clusters for AI/ML**

Whether you're an AI researcher, ML engineer, or cloud architect, don't miss this deep dive into the future of ultra-scale container orchestration.  The video looks at Amazon EKS's support for clusters with up to 100,000 nodes and show how this enables massive AI/ML workloads with up to 1.6 million AWS Trainium chips or 800,000 NVIDIA GPUs in a single Kubernetes cluster. Lots of great stuff including a look at the enhanced etc architecture with consensus offloading and in-memory database, Karpenter improvements for managing ultra-scale clusters, Network optimisations for high-performance AI/ML workloads, and more.

{{< youtube tFRWjpWIjw4 >}}

**Deploy Secure Containers on Amazon EKS with Chainguard**

In this video, Sai Vennam details how Amazon EKS Auto Mode and Chainguard’s secure-by-default container images work together to streamline Kubernetes operations and strengthen your software supply chain. This session explores how EKS Auto Mode reduces the complexity of cluster management by automatically provisioning and scaling compute resources, while Chainguard’s hardened images help eliminate vulnerabilities by default — without sacrificing developer velocity. Sai shares actionable techniques for deploying production-ready workloads with greater efficiency and security, and wraps up with a hands-on demo to show you how easy it is to get started with these tools in tandem.

{{< youtube BknFieQXSqA >}}

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes: Aaron Sempf, Joshua Toth, Matthew Berman, Thorsten Hoeger, Donnie Prakoso, David Kerber, Damon Cortesi, Janne Sinivirta, Todor Todorov, Elizabeth Fuentes, Vivek V, Sai Vennam, Roman Tsypuk, Danillo Poccia, Colin Percival, Chetan Hirapara, Marc Brooker, Alberto Crescini, Anuj Butail, Arlind Nocaj, Arron Bailiss, Arun Shanmugam, Aswin Vasudevan, Bharath Gajendran, Brenno Passanha, Cade Kettner, Chirantan Pandya, Chris Gillespie, Christina Andonov, Divya Gupta, Doruk Ozturk, Dumlu Timuralp, Felix John, Gladwin Neo, Gunjan Jain, Hari Charan Ayada, Ioannis Moustakis, Jan Michael Go Tan, Kamen Sharlandjiev, Kamilo "Kam" Amir, Kinshuk Pahare, Krishna Sarabu, Linda O'Connor, Lorenzo Nicora, Lotfi Mouhib, Mahak Arora, Majdoulina Makbal, Malte Reimann, Manoj Jayadevan, Manojit Saha Sardar, Mihir Surani, Nicolas Jourdan, Nikita Ravi Shetty, Nirupam Datta, Pratik R. Mankad, Pushkar Patil, Rahul Easwar, Raviteja Sunkavalli, Rizwan Mushtaq, Ryan Moore, Sasi Kiran Malladi, Sean Bjurstrom, Shivam Dubey, Sofie Zilberman, Suba Palanisamy, Sunil Ramachandra, Suthan Phillips, Thomas Sceifers, Utkarsh Pundir, Vincent Gromakowski, Vinod Jayendra, Yuriy Prykhodko, Forest Vey, Greg Fina, Jason Janiak, Kai Wombacher, Matt Poland, Mike Stefaniak, Peter Manastyrny, Suvojit Dasgupta, Trevor Bonas, and Victor Servin


### Stay in touch with open source at AWS

Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) for more open source goodness.

One of the pieces of feedback I received was to create a repo where all the projects featured in this newsletter are listed. Where I can hear you all ask? Well as you ask so nicely, you can meander over to[ newsletter-oss-projects](https://aws-oss.beachgeek.co.uk/3l8).

Made with ♥ from DevRel