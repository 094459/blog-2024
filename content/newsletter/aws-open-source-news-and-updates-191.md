---
title: 'AWS open source newsletter #191'
date: '2024-03-04'
tags : [ oss-newsletter, aws open source, PostgreSQL, Kubernetes, Amazon EKS, Amazon Corretto, SnapStart, AWS CDK, AWS Distro for OpenTelemetry, ADOT, Karpenter, Apache Airflow, Mountpoint for S3, OpenSearch, MySQL, MariaDB, FFmpeg, Open Job Description, OpenTelemetry, Fluent Bit, Amazon Linux, Finch, aws-lite, AWS Amplify]
canonicalUrl: "https://community.aws/content/2dDZrGlFBMaPpisO4DBdSMWXjDU/aws-open-source-newsletter-191"
---

##  Edition #191

Welcome to issue #191 of the AWS open source newsletter, the newsletter where we try and provide you the best open source on AWS content.  As always, this week we start with a round up of some freshly baked new projects for you to practice your four freedoms. This week we have projects that cover AWS Nitro Enclaves, open source mapping libraries, how to grab secrets into your application configuration files, database performance benchmarking and analysis, improving the logging your applications generate, and a number of very handy tools to help you manage security data from the command line. If that is not enough to keep you all busy, we also have some great content that features projects like PostgreSQL, Kubernetes, SnapStart, AWS CDK, AWS Distro for OpenTelemetry, Karpenter, Apache Airflow, Mountpoint for S3, OpenSearch, MySQL, MariaDB, FFmpeg, Open Job Description, OpenTelemetry, Fluent Bit, Amazon Linux, Finch, aws-lite, and AWS Amplify. Plenty of open source awesomeness to keep you all very busy.

**Open Source Jobs**

I have not posted any of these in a while, but my colleague Davanum Srinivas [shared news on X](https://aws-oss.beachgeek.co.uk/3ou) that he is currently hiring and looking for some open source developers who want to work on Kubernetes. There are a number of roles, and the links to those are all in the tweet. So if you are looking, go check them out.

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution. The projects mentioned here do not represent any formal recommendation or endorsement, I am just sharing for greater awareness as I think they look useful and interesting!*

### Tools

**aws-secret-inject**

[aws-secret-inject](https://aws-oss.beachgeek.co.uk/3pg) this handy command line tool from Quincy Mitchell allows you to inject AWS Secrets or SSM Parameters into your configuration files (.env, or whatever you like to call your configuration files these days). The README contains examples of how you can use this. Very handy indeed.

**db-top-monitoring**

[db-top-monitoring](https://aws-oss.beachgeek.co.uk/3ph)  is lightweight application to perform realtime monitoring for AWS Database Resources. Based on same simplicity concept of Unix top utility, provide quick and fast view of database performance, just all in one screen.  The README is very details and comprehensive, so if you are doing any sort of work with databases, and need to understand the performance characteristics, this is a project you should explore.

![screen of db-top-monitoring dashboard](https://github.com/aws-samples/db-top-monitoring/blob/main/images/image03.png?raw=true)

**wide-logger**

[wide-logger](https://aws-oss.beachgeek.co.uk/3pi) is a canonical wide logger that is built to gather key, value pairs and then flush them all to the console in a single log message. This does not replace your existing detailed debug logging, it is an addition. All logs emitted by the Wide Logger will be prefixed by WIDE so you can quickly and easily find them or use filtered subscriptions to record these in a single place for easy searching and correlation. As to why you might want to use this library, then the README has you covered.

> Wide logging is a technique where you write a single log message per transaction, per service. With the WideLogger class you can add key-value metadata at any point it makes sense in your code - perhaps it's meta-data about a specific if statement that is run, the latency of an external dependency, the duration of distributed service processing or perhaps it's a version stamp linking back to the actual release artifact for your service. It can be anything at all - the more you pack in, the more cardinality you will get when trying to search data about what your system is doing. At the end of your transaction call the flush() method to write your wide log entry.

**welldone.cloud**

This week I want to share a series of projects from AWS Community Builder Michael Kirchner. I am not sure how I missed these, but they were too good not to share. (I have featured one of Mcihael's projects, so just adding here the ones I have missed)

* [aws-summarize-account-activity](https://aws-oss.beachgeek.co.uk/3pd) helps you to analyse CloudTrail data of a given AWS account and generates a summary of recently active IAM principals, API calls they made and regions that were used. The summary is written to a JSON output file and can optionally be visualised as PNG files. Michael has put together a couple of supporting blog posts for this project too.
* [aws-lint-iam-policies](https://aws-oss.beachgeek.co.uk/3pe)  runs IAM policy linting checks against either a single AWS account or all accounts of an AWS Organization. Reports on policies that violate security best practices or contain errors. Supports both identity-based and resource-based policies. Optionally dumps all policies analysed. The actual linting is performed by the AWS IAM Access Analyzer policy validation feature, which is mostly known for showing recommendations when manually editing IAM policies on the AWS Console UI. The repo provides additional blog posts to help you get started, as well as more details on how this works with supporting resources
* [aws-scps-for-sandbox-and-training-accounts](https://aws-oss.beachgeek.co.uk/3pf) is a collection of example Service Control Policies (SCPs) that are useful for sandbox and training AWS accounts. The SCPs deny API calls that change baseline account settings (contacts, billing, tax settings, etc.), have long-term financial effects (purchases and reservations) or operate outside allow-listed AWS regions or services.

### Demos, Samples, Solutions and Workshops

**aws-nitro-enclaves-eif-build-action**

[aws-nitro-enclaves-eif-build-action](https://aws-oss.beachgeek.co.uk/3pj) is a new project from AWS Hero Richard Fan that uses a number of tools to help you build a reproducible AWS Nitro Enclaves EIF (Enclave Image File). This GitHub Action use kaniko and Amazon Linux container with nitro-cli, and provides examples of how you can use other tools such as sigstore to sign artefacts as well.

**maplibregljs-amazon-location-service-route-calculators-starter**

[maplibregljs-amazon-location-service-route-calculators-starter](https://aws-oss.beachgeek.co.uk/3p9) is a new repo from AWS Hero Yasunori Kirimoto that provides an example of how you can start routing with MapLibre GL JS and Amazon Location Service. He has also put together a blog post to help get you start, [Building a Route Search Function with Amazon Location SDK and API Key Function ](https://aws-oss.beachgeek.co.uk/3pa)

### AWS and Community blog posts

Each week I spent a lot of time reading posts from across the AWS community on open source topics. In this section I share what personally caught my eye and interest, and  I hope that many of you will also find them interesting. 

**The best from around the Community**

Starting strong this week, we have AWS Community Builder Leonid Gimelshtein who puts together a short post on PostgreSQL, [Optimize DB Recovery:Multi-Thread PostgreSQL Restores on RDS](https://aws-oss.beachgeek.co.uk/3p5) that helps you to understand how to improve the efficiency of your database RTO and RPO operations. Essential reading to help destress your life! Next up we have AWS Community Builder Ant(on) Weiss who is back again, this time with the second in a series of posts he is doing around the many ways to interact with your Kubernetes clusters on Amazon EKS. To find out more about the second way, read [9 Ways to an EKS Cluster - Way 2 - AWS CLI ](https://aws-oss.beachgeek.co.uk/3p6). Sticking with Kubernetes we have Kondala Rao Patibandla, who like writing and sharing his knowledge on all things cloud native. In his post, [Automate DNS Records Creation With ExternalDNS on AWS Elastic Kubernetes Service](https://aws-oss.beachgeek.co.uk/3p7), he shares how to automate the process of creating and configuring DNS records in Route 53 using ExternalDNS and Ingress on Amazon EKS.

AWS Community Builder Vadym Kazulkin is continuing his fine series of posts that dives deeper into Java performance optimisation, in the post [AWS SnapStart - Part 16 Measuring cold and warm starts with Java 21 using different asynchronous HTTP clients ](https://aws-oss.beachgeek.co.uk/3p8). It goes without saying, make sure you start from the first post if you somehow missed this series, its great stuff. To wrap up  things this week we have AWS Hero Rehan van der Merwe with a must read post, [AWS CDK starter project - Configuration, multiple environments and GitHub CI/CD](https://aws-oss.beachgeek.co.uk/3pb) which aside from proving that naming blog posts is the hardest job about writing blog posts, helps you through the thought process and reasoning involved in setting up a CDK starter project, covering topics like configuration, environments, build systems, CI/CD processes and GitHub Workflows. As always, Rehan provides supporting code. Great stuff!

**Kubernetes**

A couple of cloud native posts caught my eye last week. First up was Hareesh Iyer and Anil Chinnam who put together [Enhance Kubernetes Operational Visibility with AWS Chatbot](https://aws-oss.beachgeek.co.uk/3p3) where they  describe how to monitor Amazon EKS workloads in near real-time from customer’s chat channels using AWS Distro for OpenTelemetry (ADOT),  Amazon CloudWatch and AWS Chatbot. They cover the integration with Microsoft Teams, so if you are using Teams and Amazon EKS, then check this one out. [hands on]

Following that was the post [How Grover saves costs with 80% Spot in production using Karpenter with Amazon EKS](https://aws-oss.beachgeek.co.uk/3p4) from Mehdi Yosofie and Suraj Nair, (Sr. DevOps Engineer at Grover). In this case study, Grover share how they were able to use Karpenter to significantly reduce their Amazon EKS cluster management overhead, and combined with Amazon EC2 cost savings in the long run, were able to increase Spot usage by 25%, increasing their usage to around 80% Spot instances in production. Pretty cool stuff. 

**Other posts and quick reads**

* [Improve the speed and cost of HPC deployment with Mountpoint for Amazon S3](https://aws-oss.beachgeek.co.uk/3p0) dives deep into understanding the performance characteristics of using Mountpoint for Amazon S3 using the Community Recipe Library for HPC Infrastructure on AWS, testing access speeds for reading files of varying sizes stored in Amazon S3 [hands on]
* [Use Amazon OpenSearch Ingestion to migrate to Amazon OpenSearch Serverless](https://aws-oss.beachgeek.co.uk/3oy) outlines the steps to make migrate the data between provisioned OpenSearch Service domains and OpenSearch Serverless [hands on]
* [Enable advanced search capabilities for Amazon Keyspaces data by integrating with Amazon OpenSearch Service](https://aws-oss.beachgeek.co.uk/3p2) explores the process of integrating  Amazon Keyspaces and Amazon OpenSearch Service using AWS Lambda and Amazon OpenSearch Ingestion to enable advanced search capabilities [hands on]
* [Trigger an AWS Lambda function from Amazon RDS for MySQL or Amazon RDS for MariaDB using audit logs and Amazon CloudWatch](https://aws-oss.beachgeek.co.uk/3oz) provides a hands on guide to show you how to invoke Lambda functions from Amazon Relational Databases Service (Amazon RDS) for MySQL and Amazon RDS for MariaDB [hands on]
* [Perform cross-account major version upgrades from Amazon RDS for MySQL 5.7 to Amazon Aurora 3.04.x with minimum downtime](https://aws-oss.beachgeek.co.uk/3ow)  guides you through the process of upgrading your RDS MySQL 5.7 database to Aurora (compatible with MySQL 8.0.x) from one account to another with minimal downtime [hands on]
* [Getting started with Open Job Description from “Hello World” to FFmpeg](https://aws-oss.beachgeek.co.uk/3ox) shows you how to describe, validate, and run complex compute jobs with OpenJD [hands on]

![open job description pipeline diagram](https://d2908q01vomqb2.cloudfront.net/fb644351560d8296fe6da332236b1f8d61b2828a/2024/02/27/OJD-Image-1.png)

* [.NET Observability with OpenTelemetry – Part 2: Logs using Fluent Bit and Amazon OpenSearch](https://aws-oss.beachgeek.co.uk/3p1) is the second in a series of posts that shows how to use NLog in a dotnet6 application to generate application logs, using FireLens and AWS for Fluent Bit to send logs to Amazon OpenSearch Service [hands on]

![.NET Observability with OpenTelemtry architecture](https://d2908q01vomqb2.cloudfront.net/b4c96d80854dd27e76d8cc9e21960eebda52e962/2024/02/22/V1217692268-01.png)

### Quick updates

**Apache Airflow**

Amazon Managed Workflows for Apache Airflow (MWAA)  is a managed orchestration service for Apache Airflow that makes it easier to set up and operate end-to-end data pipelines in the cloud.  You can now create Apache Airflow version 2.8 environments on Amazon MWAA. Apache Airflow 2.8 is the latest minor release of the popular open-source tool that helps customers author, schedule, and monitor workflows. Apache Airflow 2.8 introduces several notable enhancements like Airflow ObjectStore for seamless integration with widely-used cloud storage solutions, enhanced task logging for easier troubleshooting, and a more intuitive interface for data transfers between tasks. This update also brings in important security updates and bug fixes that enhance the security and reliability of your workflows. You can launch a new Apache Airflow 2.8 environment on Amazon MWAA with just a few clicks in the AWS Management Console in all currently supported Amazon MWAA regions.

Mansi Bhutada and Hernan Garcia have put together essential reading to dive deeper into this, so make sure you check out [Introducing Amazon MWAA support for Apache Airflow version 2.8.1](https://aws-oss.beachgeek.co.uk/3ov).

![overview of new xcom in apache airflow ui](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2024/02/26/BDB-4173-image001.png)

**Amazon Linux**

Last week we announced the general availability of Amazon Linux 2023 (AL2023) on Amazon Elastic Kubernetes Service (EKS). AL2023 is the next generation of Amazon Linux from Amazon Web Services and is designed to provide a secure, stable, high-performance environment to develop and run your cloud applications. EKS customers can enjoy the benefits of AL2023 by using the standard AL2023-based EKS optimised Amazon Machine Image (AMI) with Managed Node Groups, self-managed nodes, and Karpenter. AL2023 offers several improvements over Amazon Linux 2 (AL2). For example, AL2023 takes a secure-by-default approach to help improve your security posture with preconfigured security policies, SELinux in permissive mode and IMDSv2 enabled by default. AL2023 also optimizes boot time to reduce the time from instance launch to running applications. These optimisations span the Amazon Linux kernel and beyond. For a full comparison, see Comparing Amazon Linux 2 and Amazon Linux 2023. The standard Amazon Linux 2023-based EKS optimised AMI is generally available in all AWS Regions 

**MariaDB**

Amazon Relational Database Service (Amazon RDS) for MariaDB now supports MariaDB minor versions 10.11.7, 10.6.17, 10.5.24, and 10.4.33. We recommend that you upgrade to the latest minor versions to fix known security vulnerabilities in prior versions of MariaDB, and to benefit from the bug fixes, performance improvements, and new functionality added by the MariaDB community. You can leverage automatic minor version upgrades to automatically upgrade your databases to more recent minor versions during scheduled maintenance windows. You can also leverage Amazon RDS Managed Blue/Green deployments for safer, simpler, and faster updates to your MariaDB instances.

### Videos of the week

**Local containers with AWS's Finch project**

Phil Estes of AWS joined Bret Fisher on his YouTube show DevOps and Docker to show the Finch project, which bundles the best open source tools for building and running containers locally, and how it runs on macOS and Windows WSL2.

{{< youtube BOhj6ZivN9w >}}

**Building with aws-lite**

Fresh from ServerlessDays Denver, Ryan Block and Matthew Bonig talk about an open source project that we have featured in this newsletter before, [aws-lite](https://dev.to/aws/aws-open-source-newsletter-182-2fjh). aws-lite is simple, fast, extensible Node.js client for interacting with AWS services. Watch this video to dive deeper into this project.

{{< youtube HHGHEb1taI8 >}}

**Use AWS Amplify Gen 2 To Create A Full Stack App: With Type Safety**

Erik Hanchett walks you through how create a Full Stack app using AWS Amplify Gen2. 

{{< youtube _htSwKMdk2Y >}}

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

So thank you to the following open source heroes: Richard Fan, Quincy Mitchell, Robert Daly, Guy Baulch,  Sudhakar Darse, Sean Wallitsch, Muthu Pitchaimani, Prashant Agrawal, Rahul Sharma, Asad Aazam, Scott Ma, Ashish Bhatia, David Kilzer, Rajesh Kantamani, Sylvia Qi, Mehdi Yosofie, Suraj Nair, Hareesh Iyer, Anil Chinnam, Mansi Bhutada, Hernan Garcia, Phil Estes, Bret Fisher, Ryan Block and Matthew Bonig, Erik Hanchett,  Leonid Gimelshtein, Ant(on) Weiss,  Kondala Rao Patibandla,  Vadym Kazulkin, Hero Rehan van der Merwe,  Yasunori Kirimoto, and Michael Kirchner.

**Feedback**

Please please please take 1 minute to [complete this short survey](https://www.pulse.aws/promotion/10NT4XZQ). 

### Stay in touch with open source at AWS

Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) for more open source goodness.

One of the pieces of feedback I received in 2023 was to create a repo where all the projects featured in this newsletter are listed. Where I can hear you all ask? Well as you ask so nicely, you can meander over to[ newsletter-oss-projects](https://aws-oss.beachgeek.co.uk/3l8).

Made with ♥ from DevRel