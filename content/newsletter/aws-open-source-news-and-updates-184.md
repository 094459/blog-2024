---
title: 'AWS open source newsletter #184'
date: '2024-01-15'
tags : [ oss-newsletter, aws open source, Cedar, AWS CDK, Powertools for AWS Lambda, .NET Core, Amazon EKS, Kubernetes, Aperf, Apache Iceberg, Streamlit, Redis, Langchain, FFmpeg, Istio, Apache Flink, AWS Distro for OpenTelemetry, Prometheus,  AWS ParallelCluster, MySQL, Memcached, OpenSearch, WordPress, Linux, Finch, Redis]
canonicalUrl : "https://community.aws/content/2arO7cYup4ShOVguSMZfHt9WgJa/aws-open-source-newsletter-184"
---

###  Edition #184

Welcome to issue #184 of the AWS open source newsletter, the newsletter where we try and provide you the best open source on AWS content. 

As always, this week we start with a round up of some freshly baked new projects for you to practice your four freedoms. This week we have a rust based cli tools to help you accelerate your S3 searches, we take a look at a new framework to help simplify bootstrapping your projects, a tool to help you report on your AWS resource tags, a voice translator for Chime, a really nice sample project to help you get hands on with Cedar, a number of generative AI demos and sample projects that are a must, and many more projects. You have all been very busy I can see.

Also featured this week are posts, videos, discussion threads covering some of your favourite open source projects, which this week include Cedar, AWS CDK, Powertools for AWS Lambda, .NET Core, Kubernetes, Aperf, Apache Iceberg, Streamlit, Redis, Langchain, FFmpeg, Istio, Apache Flink, AWS Distro for OpenTelemetry, Prometheus,  AWS ParallelCluster, MySQL, Memcached, OpenSearch, WordPress, Linux, Finch, and Redis.

When I was small I was always told to never skip my vegetables, so heed this excellent advice and do not skip the Events section at the end!  I have added a new link to a repo that lists open source events that are coming up in 2024, which is well worth checking out.

**Feedback**

Please please please take 1 minute to [complete this short survey](https://www.pulse.aws/promotion/10NT4XZQ). 

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes: Bervianto Leo Pratama, Rahul Pulikkot Nath, Jason Andrews, Rajit Paul, Fady, Anup Sivadas, Abhishek Gupta, Pontus Palmenäs, Kevin Hakanson, Alejandro Gil, Joseba Echevarría, James Fogel,  Doug Youd, Nima Fotouhi, Sandeep Singh, Praseeda Sathaye, Sourav Paul, Tiago Reichert, Avinash Reddy Thipparthi , and Akhil Mohan

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution. The projects mentioned here do not represent any formal recommendation or endorsement, I am just sharing for greater awareness as I think they look useful and interesting!*

#### Tools

**s3-fast-list**

[s3-fast-list](https://aws-oss.beachgeek.co.uk/3k6) is a rust based tool that concurrently list Amazon S3 bucket with ListObjectsV2 API. Check out the README for use cases as to when s3-fast-list is going to help you out (against existing options you have)

**aws-pdk**

[aws-pdk](https://aws-oss.beachgeek.co.uk/3jb) the AWS Project Development Kit (AWS PDK) is an open-source tool to help bootstrap and maintain cloud projects. It provides building blocks for common patterns together with development tools to manage and build your projects. The AWS PDK lets you define your projects programatically via the expressive power of type safe constructs available in one of 3 languages (typescript, python or java). Under the covers, AWS PDK is built on top of Projen. The AWS Bites Podcast provides an overview of the AWS Project Development Kit (PDK), and the hosts discuss what PDK is, how it can help generate boilerplate code and infrastructure, keep configuration consistent across projects, and some pros and cons of using a tool like this versus doing it manually.

{{< youtube zcsKORL-nXc >}}

**aws-organizations-tag-inventory**

[aws-organizations-tag-inventory](https://aws-oss.beachgeek.co.uk/3jz)  This project provides a solution to AWS customers for reporting on what tags exists, the resources they are applied to, and what resources don't have tags across their entire AWS organization. The solution is designed to be deployed in an AWS Organization with multiple accounts. Detailed information and deployment guidelines are in the README, including some sample dashboards so you can see what you can expect.

![architecture of aws-org tagging inventory](https://github.com/aws-samples/aws-organizations-tag-inventory/blob/main/images/architecture.drawio.png?raw=true)

**appfabric-data-analytics**

[appfabric-data-analytics](https://aws-oss.beachgeek.co.uk/3k3) this project enables you to maintain logs from various SaaS applications and provides the ability to search and display log data. This solution leverages AWS AppFabric to create a data repository that you can query with Amazon Athena. While customers can obtain normalized and enriched SaaS audit log data (OCSF) from AppFabric, many prefer not only to forward these logs to a security tool. Some have the requirement to preserve logs for post-incident analysis, while others need to utilize the logs for tracking SaaS subscription and license usage. Additionally, some customers aim to analyze user activity to discover patterns. This project establishes a data pipeline that empowers customers to construct dashboards on top of it.

![architecture of appfabric data anlaytics](https://github.com/aws-samples/appfabric-data-analytics/blob/main/diagrams/AppFabricDataAnalyticsArchitecture.png?raw=true)

**amazon-chime-sdk-voice-voice-translator**

[amazon-chime-sdk-voice-voice-translator](https://aws-oss.beachgeek.co.uk/3k4) this project leverages the Amazon Chime SDK to create a voice to voice live translator. It facilitates real time translation in voice calls enabling seamless communication between participants speaking different languages. The system integrates various AWS services, including Amazon Chime SDK, Amazon Kinesis Video Streams (KVS), Amazon Transcribe, Amazon Translate, Amazon Polly, etc. to achieve efficient and accurate translation.

![architecture for chime voice recorder and translator](https://github.com/aws-samples/amazon-chime-sdk-voice-voice-translator/blob/main/images/MeetingOverview.png?raw=true)

**s3-presignedurl-staticips-endpoint-with-cdk**

[s3-presignedurl-staticips-endpoint-with-cdk](https://aws-oss.beachgeek.co.uk/3k5) this solution simplifies access to Amazon S3 by creating secure, custom presigned URLs for object downloads through a single endpoint with a unique domain and static IPs. The use case involves users following an IP and domain Allowlist firewall policy, limiting API access to specific domains and IPs. The architecture employs key AWS services, including AWS Global Accelerator, Amazon API Gateway, AWS Lambda, Application Load Balancer(ALB), VPC Endpoint, and Amazon S3. This design centralizes the API for generating presigned URLs and the S3 endpoint under a single domain, linked to an AWS Global Accelerator with two static IPs. Consequently, users can effortlessly request presigned URLs and download S3 objects through a unified domain endpoint with static IPs. This architecture is especially beneficial for customers with strict policies or compliance requirements, such as those in the public, medical, and finance sectors.

![overview of s3-presigned-url architecture](https://github.com/aws-samples/s3-presignedurl-staticips-endpoint-with-cdk/blob/main/architecture.png?raw=true)

#### Demos, Samples, Solutions and Workshops

**avp-toy-store-sample**

[avp-toy-store-sample](https://aws-oss.beachgeek.co.uk/3jw) is a great sample project if you want to explore Cedar, and how this fits in with Amazon Verified Permissions. This sample web application demonstrates authentication and policy-based authorization for different user types to an imaginary toy store. The toy store takes orders online and then send them to customers through multiple warehouses. This application is used by warehouses to help sending orders to customers. The application uses Amazon Cognito for authentication and uses Amazon Verified Permissions for policy-based authorization. Additionally, the application uses API-Gateway as the front-door to the application, and Lambda to process requests.

**amazon-bedrock-serverless-prompt-chaining**

[amazon-bedrock-serverless-prompt-chaining](https://aws-oss.beachgeek.co.uk/3jy) this repository provides examples of using AWS Step Functions and Amazon Bedrock to build complex, serverless, and highly scalable generative AI applications with prompt chaining.

**bedrock-multi-tenant-saas**

[bedrock-multi-tenant-saas](https://aws-oss.beachgeek.co.uk/3jx) In this repository, we show you how to build an internal SaaS service to access foundation models with Amazon Bedrock in a multi-tenant architecture. An internal software as a service (SaaS) for foundation models can address governance requirements while providing a simple and consistent interface for the end users. 

![architecture of multi-tenant-saas bedrock](https://github.com/aws-samples/bedrock-multi-tenant-saas/blob/main/images/architecture_new.png?raw=true)

**eks-saas-gitops**

[eks-saas-gitops](https://aws-oss.beachgeek.co.uk/3k1) This repository offers a sample pattern to manage multi-tenancy in a Kubernetes cluster using GitOps with Flux. The provided CloudFormation template automates the deployment of necessary AWS resources and sets up an environment ready for GitOps practices.

**eks-shared-subnets**

[eks-shared-subnets](https://aws-oss.beachgeek.co.uk/3k2) this sample code demonstrates how a central networking team in an enterprise can create and share the VPC Subnets from their own AWS Account with other Workload Specific accounts. So that, Application teams can deploy and manage their own EKS clusters and related resources in those Subnets.

![architecutre of eks-shared-subnets](https://github.com/aws-samples/eks-shared-subnets/blob/main/images/eks-shared-subnets-blog.jpg?raw=true)

**geo-location-api**

[geo-location-api](https://aws-oss.beachgeek.co.uk/3k0) is a project for the .NET developers out there, that provides a NET Web API for retrieving geolocations. The  geolocation data is provided by MaxMind GeoLite2.

### AWS and Community blog posts

**The best from around the Community**

We have a really strong selection of community content for you this week. There was so much great stuff, it was really hard to narrow it down. Starting us off this week is AWS Community Builder Bervianto Leo Pratama who has put together [Have you ever used AWS CDK Explorer for VS Code? ](https://aws-oss.beachgeek.co.uk/3ju). I had not, so I took a look at the post and the video, and I am glad I did as I learned something new. Next up we have Rahul Pulikkot Nath, who put together [How To Effectively Manage Sensitive Information in AWS Lambda: Powertools Parameters](https://aws-oss.beachgeek.co.uk/3jv)  that looks at how to get started using the Lambda Powertools Parameters on .NET Core, showing you how to use it when building Lambda Functions. 

APerf (AWS Perf) is an open source command line performance analysis tool which saves you time by collecting information which is normally collected by multiple tools such as perf, sysstat, and sysctl. Why do I just casually mention this? Well as it so happens, AWS Community Builder Jason Andrews has the perfect post to dive deeper into this tool in his post, [Install Aperf for performance analysis on AWS Graviton processors](https://aws-oss.beachgeek.co.uk/3k7). Find out how you can use this tool to with Linux performance analysis. 

Next up we have a couple of posts covering EKS Pod Identities that were launched at re:Invent 2023. Fady has put together [EKS Pod Identities Explained: Managing AWS Credentials in Kubernetes Pods](https://aws-oss.beachgeek.co.uk/3k9), and Rajit Paul wrote [Exploring the new EKS Pod Identity Associations](https://aws-oss.beachgeek.co.uk/3k8) that both provide a hands on guide to help you understand your new options in managing AWS credentials in your Kubernetes clusters.

Anup Sivadas shared [Experience the power of ACID Transactions with Amazon Athena & Apache Iceberg](https://aws-oss.beachgeek.co.uk/3ka) which provides a nice easy guide on getting started with experimenting on how to build a transactional data lake on AWS using Apache Iceberg. To finish up this weeks community round up, my colleague Abhishek Gupta who shows you how to build a very nice generative AI tool that leverages Streamlit, Redis, Langchain and Kubernetes to build a chat tool that leverages large language models hosted on Amazon Bedrock. Find out how by reading the post, [Build a Streamlit app with LangChain and Amazon Bedrock](https://aws-oss.beachgeek.co.uk/3kb). That's it from the community round up this week, we will have more for you in the next edition.

**Cedar**

This weeks must read post is this collaboration between Pontus Palmenäs and Kevin Hakanson, [Automate Cedar policy validation with AWS developer toolsAutomate Cedar policy validation with AWS developer tools](https://aws-oss.beachgeek.co.uk/3js). Cedar is an open-source language that you can use to write policies and make authorization decisions based on those policies, and regular readers will note that this is one of my favorite projects at the moment (catch me at user groups and various events talking about it). Pontus and Kevin show you how to use developer tools on AWS to implement a build pipeline that validates the Cedar policy files against a schema and runs a suite of tests to isolate the Cedar policy logic. Using this approach, you can detect invalid policies and potential application permission errors earlier in the development lifecycle and before deployment. Very cool indeed. [hands on]

![cedar policy validatio dashboard example](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2024/01/08/fig2.png)

**FFmpeg**

A couple of posts caught my eye this week. First up was an [interesting thread on Reddit](https://aws-oss.beachgeek.co.uk/3ja), which if you are looking to run FFmpeg to do any sort of media processing, then you are going to find it useful. Some great, in depth responses to how to deploy FFmpeg on AWS.

We also had a post from Alejandro Gil and Joseba Echevarría, [Optimizing video encoding with FFmpeg using NVIDIA GPU-based Amazon EC2 instances](https://aws-oss.beachgeek.co.uk/3ji), that compares video encoding performance between CPUs and Nvidia GPUs to determine the price/performance ratio in different scenarios while highlighting where it would be best to use a GPU.

![benchmarking graph of FFmpeg on cpu vs gpu](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/01/04/figure-2.png)
 
**Kubernetes**

We had a bunch of nice posts this week covering your favorite container orchestrator. Starting things off is [Spark on Amazon EKS networking – Part 1](https://aws-oss.beachgeek.co.uk/3jo), a two part post from James Fogel (Pintrest) and Doug Youd that explores how Pinterest and AWS went about gathering requirements and forming tenets for a networking design project to support large scale, real-world deployments of their data platform.

From data to security next, where Nima Fotouhi and Sandeep Singh have put together [How to use AWS Secrets Manager and ABAC for enhanced secrets management in Amazon EKS ](https://aws-oss.beachgeek.co.uk/3jp) that shows you how to apply attribute-based access control (ABAC) while you store and manage your Amazon Elastic Kubernetes Services (Amazon EKS) workload secrets in AWS Secrets Manager, and then retrieve them by integrating Secrets Manager with Amazon EKS using External Secrets Operator to define more fine-grained and dynamic AWS Identity and Access Management (IAM) permission policies for accessing secrets. [hands on]

![secrets and iam in eks](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2024/01/03/AWS-Secrets-Manager-ABAC-3.png)

The final post in this roundup is [Using Istio Traffic Management on Amazon EKS to Enhance User Experience](https://aws-oss.beachgeek.co.uk/3jq), where Praseeda Sathaye, Sourav Paul, and Tiago Reichert follow up on the previous post they collaborated on that looks at traffic management strategies that can be used with Istio to help implement sophisticated deployment strategies, reduce downtime, and improve the user experience [hands on]

![istio deployment architecture on eks](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2024/01/10/Istio-architectural-overview.png)

**Other posts and quick reads**

* [Enable metric-based and scheduled scaling for Amazon Managed Service for Apache Flink](https://aws-oss.beachgeek.co.uk/3jj) provides a look at how to automatically scale up and down the number of KPUs (Kinesis Processing Units; 1 KPU is 1 vCPU and 4 GB of memory) of your Apache Flink applications with Amazon Managed Service for Apache Flink [hands on]
* [Multi-tenant monitoring across accounts and regions using Amazon Managed Service for Prometheus](https://aws-oss.beachgeek.co.uk/3jk) is an interesting case study on how one customer used AWS Observability Services to aggregate their observability data into a single pane of glass by leveraging AWS Distro for OpenTelemetry (ADOT) and Amazon Managed Service for Prometheus.

![overview of multi-tenant monitoring across accounts architecture](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2024/01/04/Picture3-2.png)

* [How Unitary achieved automatic metric collection with Amazon Managed Service for Prometheus collector](https://aws-oss.beachgeek.co.uk/3jl) shares the journey of one company in how they are utilizing Prometheus, from the initial self-managing to using managed services, and how usage has changed as the company grew - perfect if you are about to evaluate using this open source project
* [Create a Slurm cluster for semiconductor design with AWS ParallelCluster](https://aws-oss.beachgeek.co.uk/3jm)  is a hands on guide that shows you how to create a cluster on AWS using AWS ParallelCluster, that’s purpose-built for the kinds of workloads that electronic design automation (EDA) users work with every day [hands on]
* [Enhancing ML workflows with AWS ParallelCluster and Amazon EC2 Capacity Blocks for ML](https://aws-oss.beachgeek.co.uk/3jn) explores combining AWS ParallelCluster with EC2 Capacity Blocks (explaining what these are) and how this is an effective solution to solving the GPU availability constraints [hands on]
* [AWS introduces Open Job Description for render pipelines](https://aws-oss.beachgeek.co.uk/3jr) looks at a new open standard aims to make render jobs portable across any rendering pipeline, providing open specification for defining render jobs to be portable between studios and render solutions

### Quick updates
 
 **MySQL**
 
Amazon RDS for MySQL now supports MySQL Innovation Release 8.2 in the Amazon RDS Database Preview Environment, allowing you to evaluate the latest Innovation Release on Amazon RDS for MySQL. You can deploy MySQL 8.2 in the Amazon RDS Database Preview Environment that has the benefits of a fully managed database, making it simpler to set up, operate, and monitor databases. MySQL 8.2 is the latest Innovation Release from the MySQL community. MySQL Innovation releases include bug fixes, security patches, as well as new features. MySQL Innovation releases are supported by the community until the next major & minor release, whereas MySQL Long Term Support (LTS) Releases, such as MySQL 8.0, are supported by the community for up to eight years.  *[Source](https://aws-oss.beachgeek.co.uk/3jc)*

**Memcached**

Amazon ElastiCache for Memcached now supports Memcached version 1.6.22 when using the node-based deployment option. With this release, you can now design your own ElastiCache for Memcached cluster using Memcached version 1.6.22. ElastiCache Serverless for Memcached already supports Memcached version 1.6.22. This version is a cumulative update and contains all changes and improvements from open-source Memcached version 1.6.18 to 1.6.22. *[Source](https://aws-oss.beachgeek.co.uk/3jd)*

**OpenSearch**

Amazon OpenSearch Service has added support for Transport Layer Security (TLS) version 1.3 amongst its transport security options for domain endpoint security. TLS 1.3 offers customers enhanced security and performance as compared to older TLS versions. In addition, we now support perfect forward secrecy, which provides additional safeguards against eavesdropping of encrypted data, through the use of a unique random session key. *[Source](https://aws-oss.beachgeek.co.uk/3jg)*

OpenSearch Service 2.11 now supports hybrid query score normalization. It is now easier than ever for search practitioners to leverage a combination of lexical and semantic search to improve their search relevance with OpenSearch. Combining lexical and semantic search methodologies has been beneficial to leverage the strengths of each of the methods, but until now it has been challenging given the different relevancy score scale for each method. To implement hybrid search, customers had to run multiple queries independently, then normalize and combine scores outside of OpenSearch. With the launch of the hybrid query in Amazon OpenSearch Service 2.11, OpenSearch handles score normalization and combination in one query, making hybrid search easier to implement and more efficient. *[Source](https://aws-oss.beachgeek.co.uk/3je)*

**WordPress**

Amazon Lightsail now offers a simplified experience to configure your WordPress website on Lightsail. You can set up your website on your Virtual Private Server (VPS) by simply following the workflow that will configure and secure your WordPress application for you. You can use this workflow to eliminate the complexity and time spent configuring your website. You no longer need to spend time watching how-to videos or reading documents. Instead, you can use the new workflow to complete all the necessary steps involved in configuring your WordPress application. Through this workflow, Lightsail will also set up a Secure Sockets Layer (SSL) certificate to secure your website with HTTPS. *[Source](https://aws-oss.beachgeek.co.uk/3jf)*

**Linux support in AWS Systems Manager**

AWS Systems Manager now supports instances running Ubuntu 23.04, Debian 12, MacOS 14 (Sonoma), and SUSE SP5. Systems Manager customers running these operating systems versions now have access to all AWS Systems Manager Node Management capabilities, including Fleet Manager, Compliance, Inventory, Hybrid Activations, Session Manager, Run Command, State Manager, Patch Manager, and Distributor. *[Source](https://aws-oss.beachgeek.co.uk/3jh)*

### Videos of the week

**Finch: An Open Source Client for Container Development by AWS**

Akhil Mohan shares his knowledge of [Finch](https://aws-oss.beachgeek.co.uk/2aj), an open source command line client for building, running, and publishing Linux containers. This video was captured during the AWS Community Day Kochi 2023, the audio is a little low so best listened to on headphones.

{{< youtube aM9MArQRki4 >}}


**AWS Elasticache Redis Creation and redis-cli Configuration step by step process**

Avinash Reddy Thipparthi introduces you to the world of Redis, a high-performance, open-source, in-memory data store. In this video you will see how to connect to Redis from an Amazon EC2 instance, taking full advantage of AWS services. He covers topics such as how to create and launch Redis clusters, using the redis-cli, and available commands and operations within Redis.

{{< youtube wp1QnBW2kIM >}}

# Events for your diary

If you are planning any events in 2024, either virtual, in person, or hybrid, get in touch as I would love to share details of your event with readers. 

I recently found this GitHub repo, [open-source-events](https://aws-oss.beachgeek.co.uk/3jt) that is a curated set of open source events for 2024. Go check it out and see what 2024 is looking like.

**Generative AI on AWS**
**San Francisco, US 9am - 10am, 15th January**

Harrison Chase, Co-Founder and CEO at LangChain will be providing an update at this regular meetup. You can join remotely via Zoom, so if you are doing anything with LangChain or just want to keep up with the latest updates, then make sure you check this out. You can sign up and find out more details at the meetup page, [LangChain update by Harrison Chase + Quantization + Fully Sharded Data Parallel](https://aws-oss.beachgeek.co.uk/3j9)

**FOSDEM**
**Brussels, Belgium 3rd and 4th February, 2024**

FOSDEM is a free event for software developers to meet, share ideas and collaborate. Every year, thousands of developers of free and open source software from all over the world gather at the event in Brussels. There are plenty of folks from AWS that will be there, so drop me a DM if you are going and want to meet up. You don't need to register. Just turn up and join in! 

Find out more by heading to the site home page, [FOSDEM 24](https://fosdem.org/2024/)

**SOOCon 24**
**London, UK 7th and 8th February, 2024**

The State of Open Conference is back in the new year, and what better opportunity to combine with your trip to Fosdem, than come along to the wonderful Brewery in the City of London and catch up with the hundreds of open source developers, enthusiasts, hackers, and more. Check out the event page, and if you are so inclined, there is still chance to submit a talk as the call for papers (cfp) is open until the 15th of December.

You can view more at the site page, [SOOCon24](https://stateofopencon.com/)


**Cortex**
**Every other Thursday, next one 16th February**

The Cortex community call happens every two weeks on Thursday, alternating at 1200 UTC and 1700 UTC. You can check out the GitHub project for more details, go to the [Community Meetings](https://aws-oss.beachgeek.co.uk/2h5) section. The community calls keep a rolling doc of previous meetings, so you can catch up on the previous discussions. Check the [Cortex Community Meetings Notes](https://aws-oss.beachgeek.co.uk/2h6) for more info.

**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://aws-oss.beachgeek.co.uk/1az)
