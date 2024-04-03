---
title: 'AWS open source newsletter #194'
date: '2024-04-03'
tags : [ oss-newsletter, aws open source, AWS CDK, Kubernetes, Amazon EKS, Apache Kafka, Prometheus, ArgoCD, Kyverno, Karpenter, Bottlerocket, Konveyor, PostgreSQL, OpenSearch,  AWS ParallelCluster, AWS Amplify, Next.js, Apache Flink, MySQL, Amazon Corretto, Red Hat Enterprise Linux, AlmaLinux,  Amazon Linux, Cedar, InfluxDB]
canonicalUrl: "https://community.aws/content/2eZIypVFNTNHkkDzC25NajVKZJV/aws-open-source-newsletter-194"
---

##  Edition #194

Welcome to issue #194 of the AWS open source newsletter, the newsletter where we try and provide you the best open source on AWS content. Due to travelling and speaking commitments, regular readers will have noticed that I slipped up and missed a week. Normal service has been resumed, and as always, this week we start with a round up of some freshly baked new projects for you to practice your four freedoms. This week we have projects that simplify working with your AWS credentials, provide an automated way of receiving guidance to troubleshoot deployment issues, tools to help you assess the right foundational models to use, a take on the timeless top utility, but applied to data analytics workloads, as well as a number of really cool demo projects, the pick of which for me is the one that helps you get lots of information from videos, without having to watch them.  Also featured this week is content covering open source technologies that include AWS CDK, Kubernetes, Apache Kafka, Prometheus, ArgoCD, Kyverno, Karpenter, Bottlerocket, Konveyor, PostgreSQL, OpenSearch,  AWS ParallelCluster, AWS Amplify, Next.js, Apache Flink, MySQL, Amazon Corretto, Red Hat Enterprise Linux, AlmaLinux,  Amazon Linux, Cedar, and InfluxDB.

I am actually at the start of a four week trip in Asia, kicking things off in Singapore where I will be meeting with the local AWS User Group for an open source special, before heading off to Vietnam (FOSSASIA, and the local CNCF chapter), Australia (Everything Open, and a couple of meetups), and then speaking at the AWS User Group in Thailand before heading home. If you are a regular reader of this newsletter and are in this region, check out the Events section below and maybe we can meet for coffee.


### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution. The projects mentioned here do not represent any formal recommendation or endorsement, I am just sharing for greater awareness as I think they look useful and interesting!*

### Tools

**aws-rotate-key**

[aws-rotate-key](https://aws-oss.beachgeek.co.uk/3sd) is a project from AWS Community Builder  Stefan Sundin, that helps you implement security good practices around periodically regenerating your API keys. This command line tool simplifies the rotation of those access keys as defined in your local ~/.aws/credentials file. Check out the README for plenty of helpful info and examples of how you might use this.

**pristup**

[pristup](https://aws-oss.beachgeek.co.uk/3se) is along similar lines to the previous project, except this project from my colleague Dark Mesaros, provides a way to generate temporary AWS Console sign-in URLs. The purpose of this is to enable your users that do not have AWS Console access, temporary access to it without the need for a username and password. As with all of Darko's projects, excellent documentation and examples abound in the README.

**cfn-bedrock-notify**

[cfn-bedrock-notify](https://aws-oss.beachgeek.co.uk/3sc) is a new tool from my colleague Du'an Lightfoot that is a very creative an interesting way to incorporate large language models to help you troubleshoot failed Cloudformation deployments. How many times have you had a deployment fail, only to reach out to your preferred search tool to help solve the problem. Well with this project deployed, any issues are sent via SNS to Amazon Bedrock using Anthropic Claude v3, and (hopefully) the answer to your problems are returned via the email of the SNS subscriber. Nice!

![architecture of cfh-bedrock-notify](https://github.com/labeveryday-cloud-projects/cfn-bedrock-notify/blob/main/img/cfn-notify.png?raw=true)

**chronos-forecasting**

[chronos-forecasting](https://aws-oss.beachgeek.co.uk/3rh) is a family of pre-trained time series forecasting models based on language model architectures. A time series is transformed into a sequence of tokens via scaling and quantisation, and a language model is trained on these tokens using the cross-entropy loss. Once trained, probabilistic forecasts are obtained by sampling multiple future trajectories given the historical context. Chronos models have been trained on a large corpus of publicly available time series data, as well as synthetic data generated using Gaussian processes. You can check the supporting blog post [Adapting language model architectures for time series forecasting](https://aws-oss.beachgeek.co.uk/3ri), where Abdul Fatir Ansari and Lorenzo Stella provide some additional details.

![high level depiction of chronos](https://assets.amazon.science/dims4/default/030219a/2147483647/strip/true/crop/3497x1395+0+0/resize/1200x479!/format/webp/quality/90/?url=http%3A%2F%2Famazon-topics-brightspot.s3.amazonaws.com%2Fscience%2F45%2Fbf%2F885970334241859ef1558202d0dc%2Fchronos-overview.png)

**da-top-monitoring**

[da-top-monitoring](https://aws-oss.beachgeek.co.uk/3sg)  ADTop Monitoring is lightweight application to perform real-time monitoring for AWS Data Analytics Resources. Based on same simplicity concept of Unix top utility, provide quick and fast view of performance, just all in one screen.

![example dashboard of da-top](https://github.com/aws-samples/da-top-monitoring/blob/main/docs/da-top-02.png?raw=true)

**fm-leaderboarder**

[fm-leaderboarder](https://aws-oss.beachgeek.co.uk/3sf) provides resources to help you benchmark against the growing number of different models to help you find the best LLM for your own business use case based on your own tasks, prompts, and data.

![example leaderboard](https://github.com/aws-samples/fm-leaderboarder/blob/main/resources/screenshot.jpg?raw=true)

**llm-colosseum**

[llm-colosseum](https://github.com/aws-banjo/llm-colosseum) is another repo that takes a more creative look at benchmarking your LLM's, this time using a classic video arcade fighting game. My colleague Banjo has put together this repo, together with a supporting blog post, [14 LLMs fought 314 Street Fighter matches](https://aws-oss.beachgeek.co.uk/3sl). Here's who won, which is a must read this week. Check out the repo and post for videos of these LLMs playing games.


### Demos, Samples, Solutions and Workshops

**newsletter-manager-template**

[newsletter-manager-template](https://aws-oss.beachgeek.co.uk/3sa) is a project from AWS Community Builder Matteo Depascale that provides backend service orchestrations for newsletter builders. Matteo has put together a blog post, [Building a Serverless Newsletter: Your Guide to AWS and Amazon SES](https://aws-oss.beachgeek.co.uk/3sb), shares how you can use this project in order to build all the supporting infrastructure to manage your newsletters. 

**aws-real-time-web-shop-analytics**

[aws-real-time-web-shop-analytics](https://aws-oss.beachgeek.co.uk/3sh) this project delivers a code sample to experiment with real-time web analytics with a simplified online shop as web front, Apache Flink application for real-time pattern detection using Amazon Managed Service for Apache Flink, and an OpenSearch Dashboard to visualise the results using Amazon OpenSearch Service. This application is capable of ingesting click, add to cart, and purchase event from the online shop including the user that can be specified on the interface. Then the clickstream data is analysed for predefined patterns such as removing duplicates, add to cart events that are not followed by a purchase event within a specified timeframe etc. The results are then visualised in the OpenSearch Dashboard. This repository is intended to get developers started experimenting with analysing clickstream data on AWS.

![dashboard for aws real time shop analytics](https://github.com/aws-samples/aws-real-time-web-shop-analytics/blob/main/images/opensearch_dashboard.png?raw=true)

**aws-serverless-example-for-webxr**

[aws-serverless-example-for-webxr](https://aws-oss.beachgeek.co.uk/3si) This repository contains an example solution on how to enhance your WebXR applications using AWS Serverless Services, providing scalable, efficient, and seamless user experiences.

![demo screenshot of webxr](https://github.com/aws-samples/aws-serverless-example-for-webxr/blob/main/images/plugin-demo.gif?raw=true)

**video-understanding-solution**

[video-understanding-solution](https://aws-oss.beachgeek.co.uk/3sj) This is a deployable solution to help save your time in understanding videos without having to watch every video. You can upload videos and this solution can generate AI-powered summary and entities extraction for each video. It also supports Q&A about the video like "What is funny about the video?", "How does Jeff Bezos look like there?", and "What shirt did he wear?". You can also search for videos using semantic search e.g. "Amazon's culture and history". This solution extracts information from visual scenes, audio, visible texts, and detected celebrities or faces in the video. It leverages an LLM which can understand visual and describe the video frames.

You can upload videos to your Amazon Simple Storage Service (S3) bucket bucket by using AWS console, CLI, SDK, or other means (e.g. via AWS Transfer Family). This solution will automatically trigger processes including call to Amazon Transcribe for voice transcription, call to Amazon Rekognition to extract the objects visible, and call to Amazon Bedrock with Claude 3 model to extract scenes and visually visible text. The LLM used can perform VQA (visual question answering) from images (video frames), which is used to extract the scene and text. This combined information is used to generate the summary and entities extraction as powered by generative AI with Amazon Bedrock. The UI chatbot also uses Amazon Bedrock for the Q&A chatbot. The summaries, entities, and combined extracted information are stored in S3 bucket, available to be used for further custom analytics.

Check out the README for some great demo videos of this in action. Well worth exploring this demo.

![architecture for video understanding solution](https://github.com/aws-samples/video-understanding-solution/blob/main/assets/architecture.jpg?raw=true)

### AWS and Community blog posts
 
Each week I spent a lot of time reading posts from across the AWS community on open source topics. In this section I share what personally caught my eye and interest, and  I hope that many of you will also find them interesting. 

**The best from around the Community**

The community has been very busy producing open source content, and here are the pick of the posts I read over the past two weeks. This week we start with AWS Community Builder Dakota Lewallen who shares code and a blog post on how you can do multi-region deployments with AWS CDK in the post, [Multi-region Deployments with CDK](https://aws-oss.beachgeek.co.uk/3s0). Not content with just one post, Dakota also managed to put out [Three Tips for Writing CDK Tests](https://aws-oss.beachgeek.co.uk/3s9) to help you get started with adding tests to your CDK stacks.Go check them both out. When it comes to getting started with a new technology, I love posts that provide me with everything I need, and more. AWS Community Builder Julia Furst Morgado does this for folks wanting to get started with deploying applications on Kubernetes, specifically Amazon EKS, in the post [Setting Up a Kubernetes Cluster on AWS EKS With Eksctl and Deploying an App](https://aws-oss.beachgeek.co.uk/3s1). This one is worth reading. 

From Kubernetes to Apache Kafka now, and a series of posts that start with AWS Community Builder Ehi Enabs, who provides a very handy reference post with sample code, [Deploying Amazon Managed Service for Apache Kafka (Amazon MSK) with CloudFormation](https://aws-oss.beachgeek.co.uk/3s2), that does what it says on the tin. Sticking with Apache Kafka, my colleague Ricardo Ferreira has put together a series of must read posts, [Apache Kafka Partitions as Unit of Durability](https://aws-oss.beachgeek.co.uk/3s5), [Apache Kafka Partitions as a Unit of Parallelism](https://aws-oss.beachgeek.co.uk/3s4), and [Apache Kafka Partitions as Unit of Storage](https://aws-oss.beachgeek.co.uk/3s3). These are all solid gold, so make sure you read those. AWS Community Builder Priyankar Prasad joins in the Apache Kafka party with [Amazon MSK with RedPanda-Console](https://aws-oss.beachgeek.co.uk/3s6), and provides sample code and this blog post that shows you how you can deploy [RedPanda Console](https://aws-oss.beachgeek.co.uk/3s7), an open source project that is developer focused and helps you keep on top of your Apache Kafka clusters.

Finishing things this week is another post from Ehi Enabs, this time helping you to automate the provisioning of Amazon Managed Service for Prometheus (AMP) with his post, [Amazon Managed Service for Prometheus (AMP) with CloudFormation](https://aws-oss.beachgeek.co.uk/3s8). 

 **Cloud Native round up**

There were quite a few cloud native related posts this week, so I thought I would gather these up together...

* [How to Enable Secure Self-Service Amazon EKS Cluster Provisioning with ArgoCD, Kyverno, and Nirmata Policy Manager](https://aws-oss.beachgeek.co.uk/3rj) looks at one solution to help you implement self-service cluster provisioning [hands on]
* [Protecting your Amazon EKS web apps with AWS WAF](https://aws-oss.beachgeek.co.uk/3rk) describes how to use AWS WAF and AWS Firewall Manager to protect web-based workloads that run in an Amazon Elastic Kubernetes Services (Amazon EKS) cluster [hands on]
* [Applying Spot-to-Spot consolidation best practices with Karpenter](https://aws-oss.beachgeek.co.uk/3ro) provides a detailed look at how Karpenter can actively replace a Spot node with another more cost-efficient Spot node, so that you can have the right balance between lower price and low-frequency interruptions [hands on]
* [Delivering video content with fractional GPUs in containers on Amazon EKS](https://aws-oss.beachgeek.co.uk/3rt) is a great read on how to build a video encoding pipeline on AWS that uses fractional GPUs in containers using Amazon EKS, Bottlerocket, and Karpenter that could help you achieve up to 95% better price-performance [hands on]
* [Accelerate your Application Modernization to Amazon EKS with Konveyor](https://aws-oss.beachgeek.co.uk/3rw) provides an introduction to Konveyor, an open source tool that you can use in your modernisation projects on Kubernetes [hands on]

**Other posts and quick reads**

* [Identify PostgreSQL semantic issues with the plpgsql_check extension](https://aws-oss.beachgeek.co.uk/3rn) shows you how you can use the plpgsql_check extension in PostgreSQL to catch potential semantic errors and elevate your overall code quality, that may arise when translating Oracle-specific code to PostgreSQL [hands on]
* [Introducing enhanced functionality for worker configuration management in Amazon MSK Connect](https://aws-oss.beachgeek.co.uk/3rp) looks at new features that were added to MSK Connect, which streamline connector and worker management with the introduction of APIs for deleting worker configurations, tagging MSK Connect resources, and support in AWS CloudFormation to create non-default worker configurations [hands on]
* [Build an end-to-end serverless streaming pipeline with Apache Kafka on Amazon MSK using Python](https://aws-oss.beachgeek.co.uk/3rs) will help you understand how to build a serverless streaming pipeline on AWS using Amazon MSK, Lambda, DynamoDB, Amazon Data Firehose, and other services [hands on]
* [Use Generative AI and Next.js with AWS Amplify to build a Fullstack Recipe Generator](https://aws-oss.beachgeek.co.uk/3rr) walks you through how you can build an AI-powered Recipe Generator App with AWS Amplify Gen 2 and Amazon Bedrock  [hands on]

![example demo of ai powered recipe generator](https://d2908q01vomqb2.cloudfront.net/0a57cb53ba59c46fc4b692527a38a87c78d84028/2024/03/20/AIDemo.gif)

* [Amazon OpenSearch H2 2023 in review](https://aws-oss.beachgeek.co.uk/3ry) in case you missed any of the updates in the second half of 2023, then this post has you covered
* [Hybrid Search with Amazon OpenSearch Service](https://aws-oss.beachgeek.co.uk/3ru) explains the internals of hybrid search (lexical search and semantic search) and how to build a hybrid search solution using OpenSearch Service [hands on]

![hybrid search with amazon opensearch service](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2024/02/15/Picture_1_bdb3935.png)

* [Protein language model training with NVIDIA BioNeMo framework on AWS ParallelCluster](https://aws-oss.beachgeek.co.uk/3rx) demonstrates how to pre-train the ESM-1nv model with the NVIDIA BioNeMo framework using NVIDIA GPUs on AWS ParallelCluster, an open-source cluster management tool that makes it easy for you to deploy and manage HPC clusters on AWS [hands on]

![overview of architecture for developing models on NVIDIA BioNeMo](https://d2908q01vomqb2.cloudfront.net/e6c3dd630428fd54834172b8fd2735fed9416da4/2024/03/18/CleanShot-2024-03-18-at-14.36.56.png)

* [Amazon Aurora MySQL version 2 (with MySQL 5.7 compatibility) to version 3 (with MySQL 8.0 compatibility) upgrade checklist, Part 1](https://aws-oss.beachgeek.co.uk/3rz) looks at the MySQL upgrade precheck process and common issues that will cause the upgrade and upgrade prechecks to fail and how to resolve those issues

**Case Studies**

* [Krones real-time production line monitoring with Amazon Managed Service for Apache Flink](https://aws-oss.beachgeek.co.uk/3rl) is a case study that shows how AWS customer Krones built a real-time production line monitoring system on AWS using Managed Service for Apache Flink, that helped reduce machine downtime by 10% and increase efficiency up to 5%

![overview of Krones real time architecture](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2024/03/15/bdb-4037-architecture-1024x573.png)

* [How Cornerstone Built a Full-Fledged Apache Kafka Replication Using Amazon MSK Connect](https://aws-oss.beachgeek.co.uk/3rm) provides a case study that shows how Cornerstone automated the migration of Apache Kafka using a custom plugin [hands on]

### Quick updates

**Amazon Corretto**

Amazon Corretto 22 is now generally available. This version supports the latest OpenJDK feature release and is available on Linux, Windows, and macOS. You can download Corretto 22 [from our downloads page](https://aws-oss.beachgeek.co.uk/3rf). Corretto 22, an OpenJDK Feature Release, introduces a range of new capabilities and enhancements. Noteworthy additions include stream gatherers and unnamed variables, which improve code readability and maintenance. Additionally, optimisations in garbage collection algorithms contribute to improved performance. Updates to existing APIs, such as the structured concurrency, class file api and foreign function interfaces, further enrich developers' toolsets, enabling them to build more resilient and efficient Java applications. Corretto 22 is further evidence of the OpenJDK community's commitment to innovation.

**Prometheus**

Amazon Managed Service for Prometheus collector, a fully-managed agent-less collector for Prometheus metrics from Amazon EKS workloads, now supports AWS CloudFormation. Starting today, you can easily create, configure, and manage Amazon Managed Service for Prometheus collectors using CloudFormation templates. With AWS CloudFormation, you can use a programming language or simple text file to automatically configure collectors for Prometheus metrics from Amazon EKS infrastructure and applications. You can also continue utilising the Amazon Managed Service for Prometheus collector using the AWS Management Console, Command Line Interface (CLI) or API.

**Red Hat Enterprise Linux**

AWS Systems Manager now supports instances running Red Hat Enterprise Linux (RHEL) versions 8.9 and 9.3. Systems Manager customers running these operating systems versions now have access to all AWS Systems Manager Node Management capabilities, including Fleet Manager, Compliance, Inventory, Hybrid Activations, Session Manager, Run Command, State Manager, Patch Manager, and Distributor. For a full list of supported operating systems and machine types for AWS Systems Manager, see the user guide. Patch Manager enables you to automatically patch instances with both security-related and other types of updates across your infrastructure for a variety of common operating systems, including Windows Server, Amazon Linux, and Red Hat Enterprise Linux (RHEL).

**AlmaLinux**

Amazon Lightsail, you can easily get started on the cloud by choosing a blueprint and a bundle for your custom VPS application. Lightsail bundles include instances preinstalled with your preferred operating system, storage and data transfer, so you have everything you need to get up and running quickly. Amazon Lightsail now offers AlmaLinux 9, an open source, community owned and governed Linux distribution. AlmaLinux is an alternative for applications that require RHEL compatibility. Starting today, with just a few clicks, you can create a Lightsail virtual private server (VPS) of your preferred size that comes with AlmaLinux 9 preinstalled.

**Amazon Linux**

Announced a week or so ago, was the availability of the fourth quarterly update for Amazon Linux 2024, AL2023.4 as well as the Amazon Linux 2023 EKS optimized AMI. Amazon EKS customers can now use the standard AL2023-based EKS optimised Amazon Machine Image (AMI) with Managed Node Groups, self-managed nodes, and Karpenter, and is available across all supported version of Amazon EKS. To learn more about using Amazon Linux 2023 with EKS, see Amazon EKS optimised Amazon Linux AMIs.

Additionally, with the AL2023.4 release, customers can now use new packages such as mock, lustre-client, fetchmail, and smart-restart. Mock provides customers the ability to create a self-contained directory structure (known as a chroot environment), allowing customers to construct packages without impacting the primary system. Lustre file system helps optimise file access and data transfer in high-performance computing environments. Fetchmail enables customers to remotely retrieve and forward emails. Smart-restart provides a way for customers to restart services after the libraries they link against have been updated. To learn more about all features and packages in AL2023.4, [see release notes](https://aws-oss.beachgeek.co.uk/3re).

**Apache Kafka**

Amazon Managed Streaming for Apache Kafka Connect (Amazon MSK Connect) now supports the ability to delete MSK Connect worker configurations, tag resources, and manage worker configurations and custom plugins using AWS CloudFormation. Amazon MSK Connect is a fully managed service for Apache Kafka Connect. With a few clicks, MSK Connect allows you to easily deploy connectors that move data between Apache Kafka and external systems. Together, these new capabilities make it easier for you to manage your MSK Connect resources and automate deployments through CI/CD pipelines. 

When you deploy a connector on MSK Connect, you have to either use the default worker configuration or provide custom worker configuration. As you create and delete connectors, these configurations can grow in number and become difficult to manage. The new delete worker configuration API allows you to delete unused worker configurations to make resource management easier. With resource tagging, you can assign tags in the form of key-value pairs to MSK Connect connectors, custom plugins, or worker configurations. Tagging can help you with resource grouping, cost allocation and reporting, and access control with tag-based policies. Lastly, support for additional AWS CloudFormation resource types allows you to perform Create, Read, Update, Delete and List operations on custom plugins and worker configurations besides connectors.

**Apache Flink**

Amazon Managed Service for Apache Flink makes it easier to transform and analyse streaming data in real time with Apache Flink. Apache Flink is an open source framework and engine for processing data streams. Amazon Managed Service for Apache Flink reduces the complexity of building and managing Apache Flink applications and integrates with Amazon Managed Streaming for Apache Kafka (Amazon MSK), Amazon Kinesis Data Streams, Amazon OpenSearch Service, Amazon DynamoDB streams, Amazon S3, custom integrations, and more using built-in connectors. 

Amazon Managed Service for Apache Flink now supports Apache Flink 1.18. This new version includes improvements to connectors including Amazon OpenSearch, Amazon DynamoDB, MongoDB, and improved watermark alignment and query performance. For a complete list of supported features, improvements, and bug fixes please see Amazon Managed Service for Apache Flink [in the documentation](https://aws-oss.beachgeek.co.uk/3rg). Also check out the supporting blog post, [Amazon Managed Service for Apache Flink now supports Apache Flink version 1.18](https://aws-oss.beachgeek.co.uk/3rv) where  Lorenzo Nicora and Francisco Morillo discuss some of the interesting new features and capabilities of Apache Flink, introduced with the most recent major releases, 1.16, 1.17, and 1.18.

You can now upgrade existing applications to new Apache Flink versions in Amazon Managed Service for Apache Flink using in-place Apache Flink version upgrades. With in-place Apache Flink version upgrades you retain application traceability across Apache Flink versions including snapshots, logs, metrics, tags, Flink configurations, resource limit increases, VPCs, and more. You can upgrade to new Apache Flink versions by selecting the application, the snapshot you want to restore from, and the new Apache Flink runtime you require using the AWS CLI, SDK, CloudFormation, or Management Console.

### Videos of the week

**Meet Cedar: Adding generation Authz for your cloud native applications**

My good chum Derek has been busy on speaking at Latency 2024 on one of my favourite topics. In this recording of his session, he walks you through an overview of the challenges of implementing authorisation that developers face, and then introduces Cedar, an open source domain specific language that helps you to solve some of those challenges.

{{< youtube QCqLuAPTvzU >}}

**Amazon Timestream for InfluxDB Manage time-series applications easily**

If you missed the announcement, Amazon Timestream introduce a new option for customers wanting to a time stream optimised database, that uses the latest open source version of InfluxDB. Join the folks from InfluxData, the Amazon Timestream GM, as well as your usual AWS on Air host, to dive into this in more detail.

{{< youtube nqRvtqRWARk >}}

### Events for your diary

If you are planning any events in 2024, either virtual, in person, or hybrid, get in touch as I would love to share details of your event with readers. 

I recently found this GitHub repo, [open-source-events](https://aws-oss.beachgeek.co.uk/3jt) that is a curated set of open source events for 2024. Go check it out and see what 2024 is looking like.

**AWS User Group Singapore**
**April 3rd, AWS Office - 23 Church Street, Capital Square**

We are running a special open source event at the AWS Singapore User Group, where Dr Aparna Sundar and myself will be speaking on open source topics (OpenSearch and Cedar). This will be the start of a mini tour of Asia, so I am looking forward to meeting the community and sharing the open source love. Places are limited, so if you are in the area then check out the sign up page on [meetup](https://www.meetup.com/aws-sg/events/299946921/) and see you on Wednesday.

**FOSSASIA**
**April 8th-10th, Hanoi, Vietnam**

The FOSSASIA Summit is one of Asia's Premier Open Technology conference with thousands of participants and an Open Tech exhibition taking place every year in March, and this year it will be in the vibrant city of Hanoi, Vietnam. A number of my AWS colleagues will be there as well as myself, so I look forward to meeting with some of you. You can find out more details about this event by checking out the [FOSSASIA event page](https://aws-oss.beachgeek.co.uk/3ni)

**Everything Open**
**April 16th-18th, Gladstone Australia**

Everything Open is an open source event where the open source community come together for three days to share updates on their projects and learn about the latest in open technologies from leading community members. The conference will cover a broad range of topics across three days. You can expect to see talks from areas such as the Linux ecosystem, including the Kernel, distros and drivers. There will also be a number of presentations on open source software and open hardware, alongside talks on Galleries, Libraries, Archives and Museums (GLAM), open data, open government, and much more. Another key feature will be talks on building and managing communities around open technologies. I will be attending and doing some open source talks, as well as finding out more about the local open source community.

Check out [the event website](https://aws-oss.beachgeek.co.uk/3nh)for more details, and hope to see some of you there.

**OpenSearchCon Europe**
**May 6th-7th, Berlin Germany**

I am happy to share news of the launch of a European edition of OpenSearchCon, so make sure you mark these dates in your diary. OpenSearchCon Europe has now joined OpenSearchCon North America on our 2024 conference schedule. Read more about the event in the post, [Announcing OpenSearchCon Europe 2024](https://aws-oss.beachgeek.co.uk/3pn)

**Cortex**
**Every other Thursday, next one 16th February**

The Cortex community call happens every two weeks on Thursday, alternating at 1200 UTC and 1700 UTC. You can check out the GitHub project for more details, go to the [Community Meetings](https://aws-oss.beachgeek.co.uk/2h5) section. The community calls keep a rolling doc of previous meetings, so you can catch up on the previous discussions. Check the [Cortex Community Meetings Notes](https://aws-oss.beachgeek.co.uk/2h6) for more info.

**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://aws-oss.beachgeek.co.uk/1az)

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes:  Stefan Sundin, Du'an Lightfoot, Abdul Fatir Ansari, Lorenzo Stella, Darko Mesaros, Ritesh Patel, Marina Novikova,Elamaran Shanmugam, Patrick Vassell, Re Alvarez-Parmar, Florian Mair, Emil Dietl, Simon Peyers, Suraj Talreja, Hari Ramesh, Sashikanta Pattanayak, Bikash Chandra Rout, Jitender Kumar, Prashant Borse, Robert Northard, Carlos Manzanedo Rueda, Chinmayi Narasimhadevara, Harita Pappu, Mo Malaka, Masudur Rahaman Sayem, Michael Oguike, Josh Hart, Evan Statton, Hajer Bouafif, Praveen Mohan Prasad,  Lorenzo Nicora, Francisco Morillo, Riccardo Freschi, Celestino Bellone, John Matthews, Marissa Powers, Ankur Srivastava, Neel Patel, Jon Handler, Muslim Abu-Taha, Aruna Govindaraju, Hajer Bouafif, Prashant Agrawa, Ehi Enabs, Priyankar Prasad, Ricardo Ferreira, Julia Furst Morgado, and Dakota Lewallen.

**Feedback**

Please please please take 1 minute to [complete this short survey](https://www.pulse.aws/promotion/10NT4XZQ). 

### Stay in touch with open source at AWS

Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) for more open source goodness.

One of the pieces of feedback I received in 2023 was to create a repo where all the projects featured in this newsletter are listed. Where I can hear you all ask? Well as you ask so nicely, you can meander over to[ newsletter-oss-projects](https://aws-oss.beachgeek.co.uk/3l8).

Made with ♥ from DevRel
