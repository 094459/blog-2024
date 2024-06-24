---
title: 'AWS open source newsletter #200'
date: '2024-06-24'
tags : [ oss-newsletter, aws open source,  O3DE, Lustre, OpenSearch, Kubernetes, Amazon EKS, MariaDB, TinkerPop, Gremlin, AWS ParallelCluster, AWS Amplify, MySQL, PostgreSQL, Apache Kafka, Hive, Amazon EMR, Locust, Ray, OpenShift, ROSA, Apache Airflow, MWAA, cfn-lint, Valkey, AWS CDK, cdktf, Keycloak, Karpenter ]
canonicalUrl: "https://community.aws/content/2iKXkQejzUlmpNb0r1NrX37AAwC/aws-open-source-newsletter-200"
---

##  Edition #200

Welcome to a milestone edition of this newsletter, number #200!! Wow, it feels like quite an achievement. Before diving into this newsletter, a big thank you for sticking with me. Time has flown by so quickly, and am looking forward to the next 100. As I have done in a few of the previous milestone issues, I wanted to share a few interesting stats from sharing open source projects with you over the past few years.

* Through the power of greyskull (ok, well maybe not, but through the awesome sed/awk tools) I have featured over 3000 contributors in this newsletter, which just blows my mind. So thank you all for creating so many amazing open source projects, blog posts, videos, and other kinds of content that I share in this open source newsletter. I remain always, very humbled by your amazingness.

* Readers have clicked on over 5K links (5121 if you are a lover of precision), with 1.76 million* engagements to access the open source projects that I share in the newsletter. I have shared a total of 1591 new open source projects over the past 199 editions of this newsletter, which is just incredible. But what are the ones that seem to attract developers attention most? Well, the current top three projects that you all seem to love are the following (If you have not checked those out, then why not find out what all the interest is about):

[*the number is probably higher as I did not track links for the first year of the newsletter]

* [iac-devtools-cli-for-cdk](https://aws-oss.beachgeek.co.uk/30h) - is command line interface tool automates many of the tedious tasks of building, adding to, documenting, and extending AWS CDK applications. 
* [aws-observability/cdk-aws-observability-accelerator](https://aws-oss.beachgeek.co.uk/31y) - The AWS Observability Accelerator for CDK is a set of opinionated modules to help you set up observability for your AWS environments
* [ariga/atlas](https://aws-oss.beachgeek.co.uk/364) -  A tool for managing database schemas (not AWS specific this one)

* When it comes to folks who read this newsletter, they come from all over the world. Ethiopia, Azerbaijan, Botswana, Tajikistan, Jordan, Costa Rica, and many many more (104 countries to be specific). The top three countries, which will probably be of no surprise, are the United States, India, and the UK. (Happy to see Spain is in the top 10!). I want to send you all a big thank you for visiting this humble newsletter, and I hope you have enjoyed what I have shared with you. It has been a privilege to share and raise awareness of some of the cool work being done by open source developers, everywhere.

* I am proud that I am always listening to developer feedback on how to improve this newsletter, including the latest change where I put together a repo that separates out all the projects featured in this newsletter. If you did not know about, or where aware, check out the [newsletter-oss-projects](https://github.com/094459/newsletter-oss-projects) repo, which is not one of my most active repos. If you are a regular GitHub user, you can also keep informed when I drop the next edition of this newsletter, as I create a new release in that repo. This is your regular reminder that all feedback is a gift, so if you have ideas you think would improve this newsletter, I want to hear about it. Please use the feedback link at the bottom of this newsletter.

I would love to hear any stories or highlights that readers have. I have five AWS open source challenge coins that I am going to send to folks who are willing to share them with me, so get in touch via the comments below.

---

I have been totally absorbed by Euro 2024 so far (tell me in the comments who you fancy, but my prediction for the final four will be Spain, Portugal, Germany and Holland - as to the winner, I will make my prediction in the next edition!), but I have still found time to source only the very best open source projects and content for you. This edition features more great open source projects for you to practice your four freedoms, including some really cool projects from our CTO Dr Werner Vogels that provides a rust based cli that will help you transcribe audio using the latest Amazon Bedrock models, plugins for MLFlow that generate Sigv4, a project to help you explore and optimise S3 file uploads, an IAM visualisation tool,  an LLM based Slackbot that provides chat directly from your slack channels, a tool for OpenSearch users to help capture user insights, a tool to help you quickly determine your RDS disk utilisation from the command line, as well as the usual assortment of other demos for you to check out.

Also in this edition we have content covering open source technologies such as O3DE, Lustre, OpenSearch, Kubernetes, MariaDB, TinkerPop, Gremlin, AWS ParallelCluster, AWS Amplify, MySQL, PostgreSQL, Apache Kafka, Hive, Locust, Ray, OpenShift, ROSA, Apache Airflow, cfn-lint, Valkey, AWS CDK, cdktf, Keycloak, and Karpenter.

As always, get in touch if you want me to feature your projects in this open source newsletter. Until the next time, I will leave you to dive into the good stuff!

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution. The projects mentioned here do not represent any formal recommendation or endorsement, I am just sharing for greater awareness as I think they look useful and interesting!*

### Tools

**sagemaker-mlflow**

[sagemaker-mlflow](https://aws-oss.beachgeek.co.uk/3ya)  This plugin generates Signature V4 headers in each outgoing request to the Amazon SageMaker with MLflow capability, determines the URL of capability to connect to tracking servers, and registers models to the SageMaker Model Registry. It generates a token with the SigV4 Algorithm that the service will use to conduct Authentication and Authorization using AWS IAM.

If you missed the announcement, you can now use MLFlow on AWS as part of the fully managed MLflow on Amazon SageMaker service. My colleague Veliswa has put together a post that walks you through this new managed service, as well as how to get started. Go check the post out,  [Announcing the general availability of fully managed MLflow on Amazon SageMaker](https://aws-oss.beachgeek.co.uk/3y9)

**distill-cli**

[distill-cli](https://aws-oss.beachgeek.co.uk/3yz) is a new project from Amazon CTO Dr Werner Vogels, which uses Amazon Transcribe and Amazon Bedrock to create summaries of your audio recordings (e.g., meetings, podcasts, etc.) directly from the command line. Distill CLI takes a dependency on Amazon Transcribe, and as such, supports the following media formats: AMR, FLAC, M4A, MP3, MP4, Ogg, WebM, WAV. It is great to feature this latest project, with the previous one being featured in [#197](https://community.aws/content/2gPNtsdSfQRIpmbUrNyPrjUg54D/aws-open-source-newsletter-197). To go with this repo, there is a post too, [Introducing Distill CLI: An efficient, Rust-powered tool for media summarization](https://aws-oss.beachgeek.co.uk/3yy) where Werner shares his experience building this tool in Rust, and provides some closing thoughts too.

![screenshot of distill-cli running in terminal](https://www.allthingsdistributed.com/images/distill-cli-header.png)

**config-rds-ca-expiry**

[config-rds-ca-expiry](https://aws-oss.beachgeek.co.uk/3z7) provides sample code to create a custom AWS Config rule to detect expiring CA certificates. Everyone loves TLS certs, but we all hate it when we realise that stuff has broken because they expired. It can happen to anyone, so check this out and make sure you are proactively managing your certs on your Amazon RDS instances, and how this is different to the out of the box notifications you already get with Amazon RDS.


**s3-diff-uploader**

[s3-diff-uploader](https://aws-oss.beachgeek.co.uk/3z0) is the latest project from open source good guy Damon Cortesi, that came about from some [experimentations](https://www.linkedin.com/posts/dacort_i-wanted-to-experiment-recently-with-incremental-activity-7206314345599832065--95_
) he was doing with incremental uploads of compressed files to S3. He decided to publish a simple proof-of-concept CLI tool that demonstrates how you can both append and compress file uploads to S3. The result so far, is it uses UploadPartCopy and the fact that you can concatenate gzip chunks to reduce the amount of data you need to upload directly.

![s3 diff upload flow](https://media.licdn.com/dms/image/D5622AQHZ97bP8MnPmw/feedshare-shrink_2048_1536/0/1719144940507?e=2147483647&v=beta&t=n-kIkTsMlrenbW32SW7_ikvHR5jMDPCmTPnnSJalPQc)

**awsviz**

[awsviz](https://aws-oss.beachgeek.co.uk/3z1) is a super nice little tool from Bour Mohamed Abdelhadi, that helps you quickly visualy your IAM policies. You can check out the hosted version of [awsviz](https://aws-oss.beachgeek.co.uk/3z3) and there are some sample policies to show you what you can expect. Check out the[ use cases doc](https://aws-oss.beachgeek.co.uk/3z4) to see why you might want to try this tool out.

You can find out more, including watching a short video on this tool, by checking out the [original LinkedIn post here](https://aws-oss.beachgeek.co.uk/3z5).

**sparklepop**

[sparklepop](https://aws-oss.beachgeek.co.uk/3z2) is a simple Python package from Daniel B designed to check the free disk space of an AWS RDS instance. It leverages AWS CloudWatch to retrieve the necessary metrics. This package is intended for users who need a straightforward way to monitor disk space without setting up complex alerts.

**user-behavior-insights**

[user-behavior-insights](https://aws-oss.beachgeek.co.uk/3yx) This repository contains the OpenSearch plugin for the User Behavior Insights (UBI) capability. This plugin facilitates persisting client-side events (e.g. item clicks, scroll depth) and OpenSearch queries for the purpose of analyzing the data to improve search relevance and user experience.

### Demos, Samples, Solutions and Workshops

**slackrock**

[slackrock](https://aws-oss.beachgeek.co.uk/3yw) is a conversational AI assistant powered by Amazon Bedrock & your favorite cutting-edge frontier models. The project is focused on cost efficiency & simplicity, while supporting a wide variety of AI models with differing strengths & weaknesses to fit the widest array of use cases. Converse with your favourite LLMs without ever leaving Slack!

Corey Lane has also put together a blog post, [Introducing Slackrock: Conversing with AI in Slack Made Easy](https://aws-oss.beachgeek.co.uk/3yv) that walks you through this project, from how it works, how to run and configure it, and more. 

![example screenshot of slackrock in action](https://assets.community.aws/a/2hu4WH0TAVEHimPHccNn6FYg4Ms/pira.webp)

**amazon-bedrock-slack-gateway**

[amazon-bedrock-slack-gateway](https://aws-oss.beachgeek.co.uk/3z8) lets you use Amazon Bedrock's generative AI to enable Slack channel members to access your organisations data and knowledge sources via conversational question-answering. You can connect to your organisation data via data source connectors and integrate it with Slack Gateway for Amazon Bedrock to enable access to your Slack channel members. It allows your users to converse with Amazon Bedrock using Slack Direct Message (DM) to ask questions and get answers based on company data, get help creating new content such as emails, and performing tasks. You can also invite it to participate in your team channels. In a channel users can ask it questions in a new message, or tag it in a thread at any point. Get it to provide additional data points, resolve a debate, or summarise the conversation and capture next steps.

**build-neptune-graphapp-cdk**

[build-neptune-graphapp-cdk](https://aws-oss.beachgeek.co.uk/3z9) this repo provides a quick example on how to build a graph application with Amazon Neptune and AWS Amplify.

![overview of graph cdk app architecture](https://github.com/aws-samples/build-neptune-graphapp-cdk/blob/main/docs/images/architecture.png?raw=true)

### AWS and Community blog posts
 
Each week I spent a lot of time reading posts from across the AWS community on open source topics. In this section I share what personally caught my eye and interest, and  I hope that many of you will also find them interesting. 

**This weeks essential reading**

* [AWS CloudFormation Linter (cfn-lint) v1](https://aws-oss.beachgeek.co.uk/3yb) walks you through some potential breaking changes for folk using cfn-lint, and covers what is changing and offers some transition guidance
* [Disaster recovery strategies for Amazon MWAA – Part 2](https://aws-oss.beachgeek.co.uk/3yf) follows up from a previous post on how to implement DR strategies for your Apache Airflow environments on AWS, this time diving deeper into implementation (with code examples) [hands on]

![MWAA DR architecture](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2024/06/05/BackupRestore-Blog-1.png)

* [Introducing the Advanced Python Wrapper Driver for Amazon Aurora](https://aws-oss.beachgeek.co.uk/3yk) provides details on how to use some of the features of the Advanced Python Wrapper Driver [hands on]


**The best from around the Community**

AWS Community Builder Stefan Weber starts us off this week, with a short post, [How to Package .NET Lambda Functions Using AWS CDK](https://aws-oss.beachgeek.co.uk/3yo), that reminds everyone that sometimes writing down something you don't do frequently, so as to have a reference for future is a great thing to do. Staying with AWS CDK for a moment, we have AWS Community Builder Sidath Munasinghe who has put together [Unleashing the Power of CDK and Terraform in Cloud Deployments](https://aws-oss.beachgeek.co.uk/3yp)  that covers a topic that I don't see much content on, which is how to use CDK to create and deploy your application and infrastructure with Terraform, using cfktf. The final CDK post in this round up comes from a friend of the AWS open source newsletter, AWS Hero Ran Isenberg. In [Amazon CloudFormation Custom Resources Best Practices with CDK and Python Examples](https://aws-oss.beachgeek.co.uk/3yr), Ran explores CloudFormation custom resources, why you need them, and their different types. Make sure you check that post out.

AWS Community Builder Jakub Wołynko caught my interest in his post on Keycloak, [Install Keycloak on ECS(with Aurora Postgresql) ](https://aws-oss.beachgeek.co.uk/3yq). I have written a few times on this topic, and from the data I have it seems to be an area of a lot of interest, so check out Jakub's post if you want another way to deploy Keycloak in your AWS environment. From Amazon ECS to Kubernetes with AWS Community Builder Arseny Zinchenko, who walks you through a number of different options on how to ssh into your Karpenter nodes in the post, [AWS: Karpenter and SSH for Kubernetes WorkerNodes](https://aws-oss.beachgeek.co.uk/3ys). The final cloud native post this week is from AWS Community Builder Romar Cablao, who has put together a beginners post on running workloads on Amazon EKS. There are lots of these kinds of posts, and I still try and check as many as I can. Occasionally you see one that helps you better understand how Kubernetes works, or even better, will help you explain it to others. Romar has done this I think, in his post, [Back2Basics: Running Workloads on Amazon EKS](https://aws-oss.beachgeek.co.uk/3yt).

To close things up this week, I have my colleague Abhisek Gupta who shares how you can get started with Valkey, in the post, [Getting started with Valkey using JavaScript](https://aws-oss.beachgeek.co.uk/3yu). Make sure you check that post out, and follow Abhishek if you want more Valkey content as I am sure you will be seeing a lot more coming up.  

**Cloud Native**

* [OpenShift Virtualization on Red Hat OpenShift Service on AWS (ROSA)](https://aws-oss.beachgeek.co.uk/3y7) dives deep into the function of OpenShift Virtualization, and how you can running OpenShift virtualisation on ROSA allows customers to add the benefit of a managed service to underpin their virtualization stack
* [Simplify EKS Cluster Deployment and Management with Kyndryl Cloud-Native Solution (KCNS)](https://aws-oss.beachgeek.co.uk/3yc) explains how to simplify, optimize, and automate container orchestration and application modernization with Kyndryl Cloud Native Services (KCNS) for EKS (Elastic Kubernetes Service) [hands on]
* [Ray Serve High Availability](https://aws-oss.beachgeek.co.uk/3y4) provides you with a detailed solution on how you can deploy a critical component of a Ray Cluster, in a highly available and resilient fashion [hands on] 
* [Host the Whisper Model with Streaming Mode on Amazon EKS and Ray Serve](https://aws-oss.beachgeek.co.uk/3yd)  shows you how to build a scalable and distributed ML inference solution using the Whisper model for streaming audio transcription, deployed on Amazon EKS and using Ray Serve [hands on]

![locust real time dashboard](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2024/06/18/Picture10-1-1024x585.png)
 
* [How to create a pipeline for hardening Amazon EKS nodes and automate updates](https://aws-oss.beachgeek.co.uk/3yh) provides a hands on guide that shows you how to create a workflow to harden Amazon EKS-optimized AMIs by using the CIS Amazon Linux 2 or Amazon Linux 2023 Benchmark and to automate the update of EKS node groups [hands on]


**Other posts to check out**

* [New – Rightsizing Recommendations for Amazon RDS MySQL and RDS PostgreSQL in AWS Compute Optimizer](https://aws-oss.beachgeek.co.uk/3y6) takes you through how you can quickly detect idle RDS resources and identify opportunities to optimise your RDS DB instance and storage usage
* [Stream multi-tenant data with Amazon MSK](https://aws-oss.beachgeek.co.uk/3y8) looks at implementation patterns a SaaS vendor can adopt when using a streaming platform as a means of integration between internal components, where streaming data is not directly exposed to third parties
* [Design a data mesh pattern for Amazon EMR-based data lakes using AWS Lake Formation with Hive metastore federation](https://aws-oss.beachgeek.co.uk/3yl) delves into the key aspects of using Amazon EMR for modern data management, covering topics such as data governance, data mesh deployment, and streamlined data discovery [hands on]

![overview of emr data lake solution with hive federation architecture](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2024/06/04/BDB-4125_2_image002.gif)

* [Deploying a web application using AWS Amplify Gen 2 with GitLab as the Repository on AWS](https://aws-oss.beachgeek.co.uk/3ye) guides you through the process of deploying a web application using GitLab as the repository and AWS Amplify Hosting as the deployment platform [hands on]
* [Optimize storage costs in Amazon OpenSearch Service using Zstandard compression](https://aws-oss.beachgeek.co.uk/3yi) explores the performance of the Zstandard algorithm, which was introduced in OpenSearch v2.9, amongst other available compression algorithms in OpenSearch [hands on]
* [Integrating Research and Engineering Studio with AWS ParallelCluster](https://aws-oss.beachgeek.co.uk/3yj) dives into a new HPC recipe which creates a Research and Engineering Studio on AWS (RES) compatible ParallelCluster login node software stack [hands on]
* [Exploring new features of Apache TinkerPop 3.7.x in Amazon Neptune](https://aws-oss.beachgeek.co.uk/3ym) explores Apache TinkerPop 3.7.x new features to the Gremlin language, and how they will help improve your ability to write graph queries in various ways [hands on]

### Quick updates

**Valkey**

The first generally available, stable Valkey release today. This release maintains the same protocol, API, return values, and data file formats with the last open source release of Redis (7.2.4). Check out the [release page for 7.2.5](https://aws-oss.beachgeek.co.uk/3yn).

**MariaDB**

Amazon Relational Database Service (Amazon RDS) for MariaDB now supports MariaDB minor versions 10.11.8, 10.6.18, 10.5.25, and 10.4.34. We recommend that you upgrade to the latest minor versions to fix known security vulnerabilities in prior versions of MariaDB, and to benefit from the bug fixes, performance improvements, and new functionality added by the MariaDB community.

**Kubernetes**

Amazon EKS has open sourced the Pod Identity agent, providing customers with more options to package and deploy the agent into EKS clusters. Pod Identity is a feature of EKS that simplifies the process for cluster administrators to configure Kubernetes applications with AWS IAM permissions. A prerequisite for using the Pod Identity feature is running the Pod Identity agent on the cluster’s worker nodes. With the Pod Identity agent being open sourced, you can now build the agent on your own. This gives you various options to package and deploy the agent, enabling you to align with your organisation’s deployment practices.

With access to the Pod Identity agent’s source code, you are able to inspect the source code and perform necessary scans as part of your build process. Additionally, you can choose to package and deploy the pod identity agent as a binary in your custom EKS AMI. Alternatively, you can build a container image from source code, and store it in your preferred container registry. You can then deploy the containerised agent using a Helm chart or as a Kubernetes manifest file.

If you are interested in diving straight to the source code, you can grab that here - [eks-pod-identity-agent](https://aws-oss.beachgeek.co.uk/3z6)

**OpenSearch**

Amazon OpenSearch Serverless now offers customers the option to use Internet Protocol version 6 (IPv6) addresses for the endpoint of your OpenSearch Serverless collection. Customers moving to IPv6 can simplify their network stack by enabling their OpenSearch Serverless endpoints with both IPv4 and IPv6 addresses. The continued growth of the internet is exhausting available Internet Protocol version 4 (IPv4) addresses. IPv6 increases the number of available addresses by several orders of magnitude, so customers will no longer need to manage overlapping address spaces in their VPCs. Customers can also standardise their applications on the new version of Internet Protocol by moving their OpenSearch Serverless Endpoints to IPv6 only.

**Lustre**

Amazon FSx for Lustre, a service that provides high-performance, cost-effective, and scalable file storage for compute workloads, is increasing the maximum level of metadata IO operations per second (IOPS) you can drive on a file system by up to 15x, and now allows you to provision metadata IOPS independently of your file system’s storage capacity.

A file system’s level of metadata IOPS determines the number of files and directories that you can create, list, read, and delete per second. By default, the metadata IOPS of an FSx for Lustre file system scales with its storage capacity. Starting today, you can provision up to 15x higher metadata performance per file system—independently of your file system’s storage capacity—allowing you to scale to even higher levels of performance, accelerate time-to-results, and optimise your storage costs for metadata-intensive machine learning research and high-performance computing (HPC) workloads. You can also update your file system’s metadata IOPS level with the click of a button, allowing you to quickly increase performance as your workloads scale.

Higher metadata IOPS are available on new FSx for Lustre Persistent_2 file systems in all commercial AWS Regions where Persistent_2 file systems are available.


### Videos of the week

**Strengthen open source software supply chain security: Log4Shell to xz**

If you did not attend re:Inforce a few weeks ago, then don't worry, as some of the videos are now being posted online. My pick of the bunch is the Leadership session from Mark Ryland and David Nalley, who dive deep into lessons learned from navigating past supply chain crises, and some that almost were. You will learn actionable techniques and best practices to improve the security posture of your supply chain.

{{< youtube wyVAqYrEaFg >}}

**O3DE Overview: Features of the Open-Source AAA Game Engine**

Grzegorz Ochmańskin explores practical considerations when selecting a game engine for various development scenarios, walking you through Open 3D Engine, diving into its distinct features and capabilities, that includes live demonstration of the O3DE engine editor.

{{< youtube bx6KU26jYTU >}}

### Events for your diary

If you are planning any events in 2024, either virtual, in person, or hybrid, get in touch as I would love to share details of your event with readers. 

**BSides Exeter**
**July 27th, Exeter University, UK**

Looking forward to joining the community at [BSides Exeter](https://bsidesexeter.co.uk/) to talk about one of my favourite open source projects, Cedar. Check out the event page and if you are in the area, come along and learn about Cedar and more!

**Open Source Summit**
**September 16-18th, Vienna, Austria**

Come join my colleagues and myself at the AWS booth at the Open Source Summit Europe, which is being held in the wonderful city of Vienna. There will be a bunch of around, doing talks, open source technology demos, and just hanging out with the open source community. Be great to see some of you there.

**All Things Open**
**27-29th October, Raleigh, North Carolina**

I will be speaking at All Things Open this coming Autumn, on the topic of applying modern application techniques with your Apache Airflow environments. I am really looking forward to coming to one of my favourite tech conferences, with the amazing community that comes year in, year out. As always my colleagues will be manning the AWS booth, and I am sure we will have some cool stuff and SWAG to share with the community.

Check out and grab your ticket while they are still available at [2024.allthingsopen.org](https://2024.allthingsopen.org/)


**Cortex**
**Every other Thursday, next one 16th February**

The Cortex community call happens every two weeks on Thursday, alternating at 1200 UTC and 1700 UTC. You can check out the GitHub project for more details, go to the [Community Meetings](https://aws-oss.beachgeek.co.uk/2h5) section. The community calls keep a rolling doc of previous meetings, so you can catch up on the previous discussions. Check the [Cortex Community Meetings Notes](https://aws-oss.beachgeek.co.uk/2h6) for more info.

**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://aws-oss.beachgeek.co.uk/1az)

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes: Bour Mohamed Abdelhadi, Daniel B, Mark Ryland, David Nalley, Grzegorz Ochmańskin, Bowen Wang, Jimmy Yang, Ryan Niksch, Emanuele Levi, Lorenzo Nicora, Nicholas Tunney, Kevin DeJong, Veliswa Boya, Darren Lin, Frank Fan, Bonnie Ng, Shawn Zhang, Eunice Tsao, Ben-Amin York Jr., Chandan Rupakheti, Parnab Basak, Nima Fotouhi, Sarthak Aggarwal, Akash Shankaran, Mulugeta Mammo, Prabhakar Sithanandam, Praveen Nischal, Doug Morand, Jianjun Xu, Dave Cramer, Sudipta Mitra, Nanda Chinnappa, Deepak Sharma, Stephen Mallette, Abhisek Gupta,  Romar Cablao, Jakub Wołynko,  Arseny Zinchenko, Stefan Weber,  Sidath Munasinghe, and Ran Isenberg

**Feedback**

Please please please take 1 minute to [complete this short survey](https://www.pulse.aws/promotion/10NT4XZQ). 

### Stay in touch with open source at AWS

Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) for more open source goodness.

One of the pieces of feedback I received in 2023 was to create a repo where all the projects featured in this newsletter are listed. Where I can hear you all ask? Well as you ask so nicely, you can meander over to[ newsletter-oss-projects](https://aws-oss.beachgeek.co.uk/3l8).

Made with ♥ from DevRel