---
title: 'AWS open source newsletter #190'
date: '2024-02-26'
tags : [ oss-newsletter, aws open source, Ray, Bottlerocket, Amazon Linux, Kubernetes, Powertools for Lambda, OCSF, Open Cybersecurity Schema Framework, Apache Airflow, CloudQuery, .NET Core, Amazon EMR, Lustre, MySQL, Prometheus, Grafana, AWS Amplify, OpenSearch, PostgreSQL, Apache Kafka, RabbitMQ, Amazon EKS, Kubecost]
canonicalUrl: "https://community.aws/content/2ctjLpDZ1fMnC821zc1lLuWs64u/aws-open-source-newsletter-190"
---

##  Edition #190

Welcome to issue #190 of the AWS open source newsletter, the newsletter where we try and provide you the best open source on AWS content. 

As always, this week we start with a round up of some freshly baked new projects for you to practice your four freedoms. This week we have projects that can help you keep on top of your cost optimisation, a tool to help you automate Well Architected reviews, a tool to help you map out your RDS instances, as well as sample projects and demos. Also featured in this weeks issue are projects that include Ray, Bottlerocket, Amazon Linux, Kubernetes, Powertools for Lambda, Open Cybersecurity Schema Framework (OCSF), Apache Airflow, CloudQuery, .NET Core, Amazon EMR, Lustre, MySQL, Prometheus, Grafana, AWS Amplify, OpenSearch, PostgreSQL, Apache Kafka, RabbitMQ, and Kubecost.

Make sure you stick to the very end and check out the Events section at the end - and if you are running an open source event and want me to include it for broader visibility, please drop me a message at ricsue at amazon dot com.

**Feedback**

Please please please take 1 minute to [complete this short survey](https://www.pulse.aws/promotion/10NT4XZQ). 

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution. The projects mentioned here do not represent any formal recommendation or endorsement, I am just sharing for greater awareness as I think they look useful and interesting!*

### Tools

**ccExplorer**

[ccExplorer](https://aws-oss.beachgeek.co.uk/2ic) (Cloud cost explorer) from AWS Community Builder Colin Duggan is a simple command line tool to explore the cost of your cloud resources. It's built on opensource tools like aws-sdk-go-v2, cobra, go-echarts, go-openai and go-pretty. It lets you quickly surface cost and usage metrics associated with your AWS account and visualize them in a human-readable format like a table, csv file, or chart. It was created so I could quickly explore and reason about service costs without switching context from the command line. It's not designed as a replacement for the official AWS COST Explorer CLI but does provide some nice features for visualisation and sorting. The CLI now supports writing cost reports to Pinecone vector database using the flag -p pinecone. The resulting index can be easily integrated with Langchain for more interesting ways to explore the data.

**service-screener-v2**

[service-screener-v2](https://aws-oss.beachgeek.co.uk/3ol) Service Screener is a tool for AWS customers to analyse their AWS accounts against best practices for architecture. It provides an easy-to-use report with recommendations across various areas like cost optimisation and security, highlighting quick fixes that are cost-effective and downtime-free. Service Screener checks environments against the Well-Architected framework and other standards, such as the Foundational Technical Review and Startup Security Baseline, offering a comprehensive, stylish report that's cost-free and easy to understand, often running within minutes. Check out the README for lots of examples and explainer videos.

**aws-az-mapper**

[aws-az-mapper](https://aws-oss.beachgeek.co.uk/3om) is a new tool from Jeremy Barnes that maps an AWS Account and it's regions physical availability zones to their logical availability zone. This project is new to me (although was released a while ago) and what got my interest was this blog post, [Tool - AWS Availability Zone Mapper](https://aws-oss.beachgeek.co.uk/3on) where Jeremy walks you through how you can use this tool, to help with our cost optimisation strategies.

**duplicate-rule-detection-tool**

[duplicate-rule-detection-tool](https://aws-oss.beachgeek.co.uk/3oq) is a project to assess the current active AWS Config rules with potential duplicate scope in an AWS account. Our goal is to help customers can make informed decisions on how to streamline their AWS Config rules and reduce complexity. Plenty of examples and detailed breakdown of how this works in the README, so give it a look.

### Demos, Samples, Solutions and Workshops

**s3-prefix-level-kms-keys**

[s3-prefix-level-kms-keys](https://aws-oss.beachgeek.co.uk/3os) is a demo of an approach to enforce Prefix level KMS keys on S3. At the moment, S3 supports default bucket keys that is used automatically to encrypt objects to that bucket. But no such feature exists for prefixes, (i.e) you might want to use different keys for different prefixes within the same bucket (rather than one key for the entire bucket). This project shows a potential solution on how to enforce prefix level KMS keys.

![architecture for s3-prefix kms project](https://github.com/aws-samples/s3-prefix-level-kms-keys/blob/main/flow.png?raw=true)

**guidance-for-natural-language-queries-of-relational-databases-on-aws**

[guidance-for-natural-language-queries-of-relational-databases-on-aws](https://aws-oss.beachgeek.co.uk/337) this AWS Solution contains a demonstration of Generative AI, specifically, the use of Natural Language Query (NLQ) to ask questions of an Amazon RDS for PostgreSQL database. This solution offers three architectural options for Foundation Models: 1. Amazon SageMaker JumpStart, 2. Amazon Bedrock, and 3. OpenAI API. The demonstration's web-based application, running on Amazon ECS on AWS Fargate, uses a combination of LangChain, Streamlit, Chroma, and HuggingFace SentenceTransformers. The application accepts natural language questions from end-users and returns natural language answers, along with the associated SQL query and Pandas DataFrame-compatible result set.

![demo of nlq using rds databases](https://github.com/aws-solutions-library-samples/guidance-for-natural-language-queries-of-relational-databases-on-aws/blob/main/pics/nlq_animation.gif?raw=true)

**text-to-sql-bedrock-workshop**

[text-to-sql-bedrock-workshop](https://aws-oss.beachgeek.co.uk/3ot) provides a workshop is designed to be a progression of Text-to-SQL techniques, starting with robust prompt engineering. This is a great follow on from the previous project if you are looking to explore generative AI and SQL, and the README provides details of how you can get started and deploy all the necessary resources.

**quickstart-for-amazon-q**

[quickstart-for-amazon-q](https://aws-oss.beachgeek.co.uk/3oo) provides an essential resources if you want to learn more about how you can use Amazon Q in your IDE. This is a very quick guide, but will help you get up and running and should provide everything you need to begin your experimentation. The great thing about this is that even if you do not have an AWS Account, you can sign up for a Builder ID and still use this.

**building-reactjs-gen-ai-apps-with-amazon-bedrock-javascript-sdk**

[building-reactjs-gen-ai-apps-with-amazon-bedrock-javascript-sdk](https://aws-oss.beachgeek.co.uk/3op) provides a sample application that integrates the power of generative AI with a call to the Amazon Bedrock API from a web application such SPA built with JavaScript and react framework. The sample application uses  Amazon Cognito credentials and IAM Roles to invoke Amazon Bedrock API in a react-based application with JavaScript and the CloudScape design system. You will deploy all the resources and host the app using AWS Amplify. Nice detailed README, so what are you waiting for, go check this out.

![demo of the rag and react demo app](https://github.com/build-on-aws/building-reactjs-gen-ai-apps-with-amazon-bedrock-javascript-sdk/blob/main/imagenes/demo-memory.gif?raw=true)

**cost-news-slack-bot**

[cost-news-slack-bot](https://aws-oss.beachgeek.co.uk/3or) is a tool written in Python that read an RSS feed and selectively publish articles, based on keywords, to Slack via Webhook.  In the example, the tool checks the AWS 'What's New' RSS feed every minute for announcements related to cost optimisation. Perfect for customising and using it for your own use cases.

### AWS and Community blog posts

Each week I spent a lot of time reading posts from across the AWS community on open source topics. In this section I share what personally caught my eye and interest, and  I hope that many of you will also find them interesting. 

**The best from around the Community**

We have a nice mix and variety in this weeks community round up, starting with AWS Community Builder Maurice Borgmeier who is bringing a ray of sunshine into all our lives with his post, [Understanding Iterations in Ray RLlib](https://aws-oss.beachgeek.co.uk/3og) where he shares his experiences with using Ray and using this on a recent Reinforcement Learning project. Fellow AWS Community Builder Ant(on) Weiss is up next, this time diving deep into Bottlerocket, a Linux-based operating system optimised for hosting containers in his post, [Exploring cgroups v2 and MemoryQoS With EKS and Bottlerocket ](https://aws-oss.beachgeek.co.uk/3oh). Ant shares important details around changes you need to be aware of, and how new distributions default to using Cgroups v2 interface for process organisation and enforcing resource limits. Ant goes onto in the post to look at how this works for EKS clusters running Kubernetes 1.26+ and what this change means for EKS users. Great stuff. Next up we have a familiar face to regulars of this newsletter, AWS Hero Ran Isenberg, who has put together [Serverless API Documentation with Powertools for AWS](https://aws-oss.beachgeek.co.uk/3oi) where he shares a method to generate OpenAPI documentation for Python Lambda function-based APIs, utilising Powertools for AWS Lambda and Pydantic. 

I was chatting with a colleague earlier this week about the [Open Cybersecurity Schema Framework (OCSF)](https://aws-oss.beachgeek.co.uk/2c1) an open-source project, delivering an extensible framework for developing schemas, along with a vendor-agnostic core security schema. So I was super happy that AWS Community Builder David Melamed put together a blog post, [A Deep Dive into OCSF & VEX - Unified Standards for Security Management](https://aws-oss.beachgeek.co.uk/3oj), that dives deeper into this - well worth reading if you want another opinion on this. To close things this week, Alina Aven has put together [Data Science Research Infrastructure with Airflow, Containers, and CICD at C2i Genomics](https://aws-oss.beachgeek.co.uk/3ok) where she shares how they deploy and run Apache Airflow in order to meet the needs of their internal data scientists. It is a great read, I really enjoyed it.

**CloudQuery**

CloudQuery is an open source tool that can help build a multi-cloud resource data lake by extracting infrastructure data from major cloud providers like AWS. This data can then be queried and analysed using AWS Glue, Amazon Athena, and Amazon Quicksight to gain actionable insights into your multi-cloud environment. Ken Haynes, Adam Nemeth, and Francesco Vergona have collaborated on a new blog post, [Building a Multicloud Resource Data Lake Using CloudQuery](https://aws-oss.beachgeek.co.uk/3o9) that provides a hands on guide on how this works, before diving in and providing a demo of this in action. Very nice post. [hands on]

![overview of architecture using cloudquery to build a data lake ](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2024/02/20/Example-architecture-diagram.png)

**.NET Core**

Good news for .NET developers, AWS Lambda now supports .NET 8 as both a managed runtime and container base image. Beau Gosse and Paras Jain have put together a post that walks you through everything you need to know about this, so head over and read on in [Introducing the .NET 8 runtime for AWS Lambda](https://aws-oss.beachgeek.co.uk/3of). [hands on]

**Other posts and quick reads**

* [Simplify authentication with native LDAP integration on Amazon EMR](https://aws-oss.beachgeek.co.uk/3oc) dives deep into the Amazon EMR LDAP authentication, showing how the authentication flow works, how to retrieve and test the needed LDAP configurations, and how to confirm an EMR cluster is properly LDAP integrated [hands on]
* [Deploying an EMR cluster on AWS Outposts to process data from an on-premises database](https://aws-oss.beachgeek.co.uk/3oa) provides a hands on guide that will show you how you can deploy an Amazon EMR cluster on AWS Outposts and use it to process data from an on-premises database [hands on]

![architecture of running amazon emr clusters on outposts](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/02/21/image-1-1.png)

* [Optimizing MMAP workloads on Amazon FSx for Lustre file systems](https://aws-oss.beachgeek.co.uk/3ob) looks at how you can increase the throughput performance capability of FSx for Lustre for memory mapping (MMAP) workloads [hands on]

![overview of general lustre comms architecture](https://d2908q01vomqb2.cloudfront.net/e1822db470e60d090affd0956d743cb0e7cdf113/2024/02/12/Figure2_Lustre_client_comm.png)

* [Migrate tables from Microsoft Access to Amazon RDS for MySQL](https://aws-oss.beachgeek.co.uk/3od) provides guidance on how to migrate tables from Microsoft Access to Amazon RDS for MySQL for the purposes of backup, migration, and data retention [hands on]
* [Monitoring Windows pods with Prometheus and Grafana](https://aws-oss.beachgeek.co.uk/3oe) walks you through how to set up Windows Exporter (a Prometheus exporter for Windows) as a Kubernetes daemonset and a PromQL (Prometheus Query Language) to enrich windows-exporter container metrics which lets you extend existing Linux-based Kubernetes monitoring to support Windows-based workloads [hands on]

### Quick updates

**AWS Amplify**

AWS Amplify Hosting now supports custom SSL certificates for custom domains. This new feature allows developers to easily upload and use their SSL/TLS certificates for their web applications hosted on Amplify, offering improved flexibility and security. With this feature, developers can now leverage certificates they've obtained from third-party Certificate Authorities (CAs) or use certificates issued by AWS Certificate Manager (ACM) to have greater control over your domain and IT compliance needs.

Matt Auerbach and Oliver Leung have put together a more comprehensive guide in their blog post, [Bring your own SSL certificate to AWS Amplify Hosting](https://aws-oss.beachgeek.co.uk/3o8)

**OpenSearch**

[OpenSearch 2.12 was announced](https://aws-oss.beachgeek.co.uk/3o6) last week, and is ready to you to download! This release increases performance for search and analytics applications and includes user experience enhancements and an array of upgrades to OpenSearch’s machine learning (ML) toolkit. The release also features OpenSearch’s integration with Apache Spark, unlocking new ways to analyse your operational data. You can find a comprehensive view of what’s new in the [2.12 release notes](https://aws-oss.beachgeek.co.uk/3o7).

**PostgreSQL**

Amazon Relational Database Service (RDS) for PostgreSQL now supports the latest minor versions PostgreSQL 16.2, 15.6, 14.11, 13.14, and 12.18. This release of RDS for PostgreSQL also includes support for pgvector 0.6.0, which adds performance improvements for building Hierarchical Navigable Small Worlds (HNSW) indexes including parallelism and in-memory builds. We recommend that you upgrade to the latest minor versions to fix the known security vulnerabilities in prior versions of PostgreSQL, and to benefit from the bug fixes, performance improvements, and new functionality added by the PostgreSQL community. You are able to leverage automatic minor version upgrades to automatically upgrade your databases to more recent minor versions during scheduled maintenance window.

**Apache Kafka**

Amazon MSK is a fully managed service for Apache Kafka and Kafka Connect that makes it easier for you to build and run applications that use Apache Kafka as a data store. You can now upgrade the Apache Kafka version of Tiered Storage enabled Amazon MSK clusters. Clusters using version v2.8.2.tiered can now upgrade in-place to the latest Apache Kafka version 3.6.0, which supports production-grade Tiered Storage in Amazon MSK. In-place upgrades use Amazon MSK’s rolling version upgrade capability, which keeps the cluster available at all times during the upgrade.

### Videos of the week

**RabbitMQ Getting Started from .NET**

Rahul Nath is your host for this session that explores some of the core concepts, features, and practical implementations of RabbitMQ, specifically focusing on its integration with .NET applications. RabbitMQ is a powerful open-source message broker facilitating communication between systems or applications. It ensures seamless data exchange by enabling asynchronous messaging, making it an essential tool for building scalable and resilient distributed systems. RabbitMQ can be hosted through self-hosted deployments, cloud providers like AWS, containerisation, managed RabbitMQ providers, and more. In this video, Rahul will be using Amazon MQ, a managed message broker service that supports ActiveMQ and RabbitMQ engine types. 

{{< youtube 4DDAGsXrNAQ >}}

**Building a Powerful Hybrid Search System**

Uploaded from OpenSearchCon 2023, Noam Schwartz explores combining text search and vector search in a hybrid setup using OpenSearc, and how you can leverage both methods to enhance search accuracy and deliver comprehensive results. 

{{< youtube ydVfgITN8g4 >}}

**Introducing Kubecost 2.0 on Amazon EKS**

In this video you will learn about KubeCost 2.0 with Webb Brown, CEO of Stackwatch (creators of KubeCost) and Sean Pomeroy, Solutions Engineer. This release introduces new features like KubeCost Network Monitoring, Actions, Forecasting, and Anomaly Detection, designed to enhance cost monitoring and management for Kubernetes, especially with EKS. You will see a demo of this running on Amazon EKS, looking at these new features, as well as how to get started.

{{< youtube YPduvtyOp48 >}}

### Events for your diary

If you are planning any events in 2024, either virtual, in person, or hybrid, get in touch as I would love to share details of your event with readers. 

I recently found this GitHub repo, [open-source-events](https://aws-oss.beachgeek.co.uk/3jt) that is a curated set of open source events for 2024. Go check it out and see what 2024 is looking like.

**FOSSASIA**
**April 8th-10th, Hanoi, Vietnam**

The FOSSASIA Summit is one of Asia's Premier Open Technology conference with thousands of participants and an Open Tech exhibition taking place every year in March, and this year it will be in the vibrant city of Hanoi, Vietnam. A number of my AWS colleagues will be there as well as myself, so I look forward to meeting with some of you. You can find out more details about this event by checking out the [FOSSASIA event page](https://aws-oss.beachgeek.co.uk/3ni)

**Everything Open**
**April 16th-18th, Gladstone Australia**

Everything Open is an open source event where the open source community come together for three days to share updates on their projects and learn about the latest in open technologies from leading community members. The conference will cover a broad range of topics across three days. You can expect to see talks from areas such as the Linux ecosystem, including the Kernel, distros and drivers. There will also be a number of presentations on open source software and open hardware, alongside talks on Galleries, Libraries, Archives and Museums (GLAM), open data, open government, and much more. Another key feature will be talks on building and managing communities around open technologies. I will be attending and doing some open source talks, as well as finding out more about the local open source community.

Check out [the event website](https://aws-oss.beachgeek.co.uk/3nh)for more details, and hope to see some of you there.

**Cortex**
**Every other Thursday, next one 16th February**

The Cortex community call happens every two weeks on Thursday, alternating at 1200 UTC and 1700 UTC. You can check out the GitHub project for more details, go to the [Community Meetings](https://aws-oss.beachgeek.co.uk/2h5) section. The community calls keep a rolling doc of previous meetings, so you can catch up on the previous discussions. Check the [Cortex Community Meetings Notes](https://aws-oss.beachgeek.co.uk/2h6) for more info.

**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://aws-oss.beachgeek.co.uk/1az)

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes: Colin Duggan, Eder de Mattos, Fernando Galves, Ken Haynes, Adam Nemeth, Francesco Vergona, Tom McDonald, Stefano Sandona, Adnan Hemani, Anant Mittal, Cezar Guimarães, Marcio Morales, Beau Gosse, Paras Jain, Maurice Borgmeier, Ant(on) Weiss, Ran Isenberg, David Melamed, Alina Aven, and Jeremy Barnes.

### Stay in touch with open source at AWS

Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) for more open source goodness.

One of the pieces of feedback I received in 2023 was to create a repo where all the projects featured in this newsletter are listed. Where I can hear you all ask? Well as you ask so nicely, you can meander over to[ newsletter-oss-projects](https://aws-oss.beachgeek.co.uk/3l8).

Made with ♥ from DevRel

