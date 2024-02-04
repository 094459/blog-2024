---
title: 'AWS open source newsletter #187'
date: '2024-02-04'
tags : [ oss-newsletter, aws open source,  Blazor, PostgreSQL, MySQL, Finch, Kubernetes, Amazon EKS, Neuronx-nemo-megatron, TensorFlow, Apache Airflow, MWAA, AWS CDK, AWS Copilot, MQTT, OpenZFS, Powertools for Lambda, Ruby, Cedar, OpenSearch, projen, openJDK, Amazon Corretto, Event Ruler]
canonicalUrl: "https://community.aws/content/2btmMsMEff1BgFGLRui76dPbVOX/aws-open-source-newsletter-1?lang=en"
---

##  Edition #187

Welcome to issue #187 of the AWS open source newsletter, the newsletter where we try and provide you the best open source on AWS content. 

As always, this week we start with a round up of some freshly baked new projects for you to practice your four freedoms. This week we have new projects that help you optimise working with EBS volumes on EC2, a tool to help you document your architectures, a large language model benchmarking tool, a tool to help you optimise your S3 storage files, a data validation framework, and a really nice Java workshop. Also featured in this weeks edition is content on projects such as  Blazor, PostgreSQL, MySQL, Finch, Kubernetes, TensorFlow, Apache Airflow, AWS CDK, AWS Copilot, OpenZFS, Powertools for Lambda, Ruby, Cedar, OpenSearch, projen, Amazon Corretto, and Event Ruler

I am particularly delighted this week in the videos, so please make sure you check those out. We have three really amazing sessions recorded that cover Cedar (my video of the week), writing Python extensions for OpenSearch, and how you can use projen to abstract your CI/CD pipelines. Great stuff.

Make sure you stick to the very end and check out the Events section at the end - and if you are running an open source event and want me to include it for broader visibility, please drop me a message at ricsue at amazon dot com.

**Feedback**

Please please please take 1 minute to [complete this short survey](https://www.pulse.aws/promotion/10NT4XZQ). 

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes:  Lasith Koswatta Gamage, David Boyne, Matt Muller, Emina Torlak, Franck Pachot, dB., Johannes Koch, Muhammad Saipul Rohman, Fiqri Ismail, Justin Alvarez, Phil Estes, Alan Halcyon, George John, Harish Kuna, Sanjeev Ganjihal, Scott Perry, Olawale Olaleye, Parnab Basak, Heitor Lessa, Noor Fairoza and Daniel Whitehead

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution. The projects mentioned here do not represent any formal recommendation or endorsement, I am just sharing for greater awareness as I think they look useful and interesting!*

### Tools

**ebs-bootstrap**

[ebs-bootstrap](https://aws-oss.beachgeek.co.uk/3mg) is a very handy tool from Lasith Koswatta Gamage that solves a very specific problem. Lasith reached out to explain more about the "itch" that needed to be scratched. ebs-bootstrap is a tool that provides a safe and as-code approach for managing block devices on AWS EC2. If you need precise and consistent control over your EBS volumes when attaching them to your EC2 Nitro based instances, you need to check out this project. The README provides some additional example configurations, and there is a blog post in the works which I will share once it has been published. Very nice work Lasith!

**cloudcatalog**

[cloudcatalog](https://aws-oss.beachgeek.co.uk/3mf) colleague David Boyne has put together another project, that is a fork of one his earlier projects ([EventCatalog](https://dev.to/aws/aws-open-source-news-and-updates-96-ig8)) that provides a similar capability, but this time helping you to document your AWS architecture. Check out the README for more details, including an example architecture that was documented. Very cool stuff indeed.

**s3-small-object-compaction**

[s3-small-object-compaction](https://aws-oss.beachgeek.co.uk/3mk) This solution deploys a serverless application to combine ("compact") small objects stored in a given Amazon S3 prefix into a single larger file. Larger files enable cost effective use of S3 storage tiers that have a minimum billable object size (e.g. 128 KB). It can also improve performance when querying data directly with Amazon Athena. The sample code is written using the AWS Cloud Development Kit in Python.

![overview of s3 small object compaction process flow](https://github.com/aws-samples/s3-small-object-compaction/blob/main/diagrams/architecture-lambda.png?raw=true)

**foundation-model-benchmarking-tool**

[foundation-model-benchmarking-tool](https://aws-oss.beachgeek.co.uk/3mj) is a Foundation model (FM) benchmarking tool. Run any model on Amazon SageMaker and benchmark for performance across instance type and serving stack options. A key challenge with FMs is the ability to benchmark their performance in terms of inference latency, throughput and cost so as to determine which model running with what combination of the hardware and serving stack provides the best price-performance combination for a given workload.

![demo of benchmark tool report](https://github.com/aws-samples/foundation-model-benchmarking-tool/blob/main/img/results.gif?raw=true)

**automated-data-validation-framework**

[automated-data-validation-framework](https://aws-oss.beachgeek.co.uk/3mi) When you are undertaking data migration projects, a significant time is spent in doing the data validation and lot of manual efforts being spent. This repo provides a framework developed that helps to simplifying this problem by automating full data validation with some simple config files, and running the framework on EMR. It will create summary and detail data validation report in S3 and show up on Athena tables. You will need to do some initial work to setup this framework and create config files which has table names to compare. Very cool indeed.

![architecture of the data validation framework](https://github.com/aws-samples/automated-data-validation-framework/blob/main/img/visual1.png?raw=true)

### Demos, Samples, Solutions and Workshops

**java-on-aws**

[java-on-aws](https://aws-oss.beachgeek.co.uk/3lx) is a fantastic resource for all Java developers who want to dive deeper on how to deploy their Java applications on AWS. Taking a sample application, the workshop looks at how you can containerise it, and then deploy it across a number of different compute environments - from serverless to Kubernetes. If you are a Java developer, do not miss this workshop!

**ecs-gpu-scaling**

[ecs-gpu-scaling](https://aws-oss.beachgeek.co.uk/3mh) This repository is intended for engineers looking to horizontally scale GPU-based Machine Learning (ML) workloads on Amazon ECS. By default, GPU utilisation metrics are not part of the predefined metrics available with Application Autoscaling. As such, you implement auto scaling based on custom metrics.  For NVIDIA-based GPUs, you use DCGM-Exporter in your container to expose GPU metrics. You can then use metrics such as DCGM_FI_DEV_GPU_UTIL and DCGM_FI_DEV_GPU_TEMP to determine your auto scaling behaviour. The README provides links to all the additional resources you need to get this up and running.

![architecture for ecs gpu scaling](https://github.com/aws-samples/ecs-gpu-scaling/blob/main/img/diagram.png?raw=true)


### AWS and Community blog posts

Each week I spent a lot of time reading posts from across the AWS community on open source topics. In this section I share what personally caught my eye and interest, and  I hope that many of you will also find them interesting. 

**The best from around the Community**

I am currently writing this in Brussels, as Fosdem is upon us. Today is [PGDay](https://aws-oss.beachgeek.co.uk/3lz) so what better way to kick things off this week than with AWS Hero Franck Pachot as he dives deep into the topic of generating unique identifiers in your application in his post, [UUID in PostgreSQL](https://aws-oss.beachgeek.co.uk/3m0). From PostgreSQL to MySQL, another popular open source database, and in [Unveiling the Power of Zero-ETL Integration between Amazon RDS for MySQL and Amazon Redshift](https://aws-oss.beachgeek.co.uk/3m2) Muhammad Saipul Rohman looks at one of the announcement from last year that helps yo simplify how you can run your extract, transform, and load operations when looking to move your data to a data warehouse. Finally for this short roundup we have AWS Community Builder Fiqri Ismail, who has put together a great post if you are interested in or currently using Blazor, an open source web frontend framework built on top of dotNET. In [The quickest way of deploying a Blazor Web Assembly app to AWS Amplify](https://aws-oss.beachgeek.co.uk/3m1), Fiqri provides a step by step guide on how to create a Blazor Web Assembly project and deploy this to AWS Amplify as a frontend. 

**Finch**

Finch is a command line client for building, running, and publishing Linux containers that I have featured in previous editions of this newsletter (and on a personal note, I have transitioned to for all my container developer needs as of 2024).  Hot off the press last week was Justin Alvarez and Phil Estes with news that you can now use Finch on Windows, in the post [Finch Container Development Tool: Now for Windows](https://aws-oss.beachgeek.co.uk/3m3)

**Kubernetes**

We had a great selection of Kubernetes related posts last week. Alan Halcyon, George John, and Harish Kuna provided some great insights in how Amazon EKS tests for scalability in the post, [How Amazon EKS approaches Scalability](https://aws-oss.beachgeek.co.uk/3m4)

![example dashboard of kubernetes pod performance](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2024/01/29/load-testing.jpg)

Sanjeev Ganjihal and Scott Perry are up next, showing you how you can use AWS Trainium with Neuronx-nemo-megatron on Amazon EKS to tackle the rising computational demands and cost challenges in training advanced AI models. If that sounds like something you need to know more about, then dive into [Train Llama2 with AWS Trainium on Amazon EKS](https://aws-oss.beachgeek.co.uk/3m5)

![tensorboard dashboard showing training](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2024/01/28/view-your-training-progress.jpg)

The final post in this round up is [Enabling mTLS with ALB in Amazon EKS](https://aws-oss.beachgeek.co.uk/3mb) where Olawale Olaleye walks you through a solution that shows you how to enable mutual TLS at ALB created by a Kubernetes Ingress resource for an application running in Amazon EKS using a self-signed generated certificates [hands on]

![architecture of solution to enable mTLS with ALB](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2024/02/01/mTLS-support.jpg)

**Apache Airflow**

My good friend Parnab Basak has created some great content for Apache Airflow users, and he is back again with an update to [Deploying to Amazon Managed Workflows for Apache Airflow with CI/CD tools](https://aws-oss.beachgeek.co.uk/s6). This is a very detailed and comprehensive guide, and will show you how you can extend existing CI/CD processes and tools to deploy code to Amazon MWAA.  Nice! [hands on]

**Other posts and quick reads**

* [Use the tds_fdw extension to migrate data from SQL Server to PostgreSQL](https://aws-oss.beachgeek.co.uk/3m6) provides a hands on guide on how to use the tds_fdw extension to migrate data from SQL Server to PostgreSQL, as well as how to address known issues related to the DATE data type in SQL Server [hands on]
* [A new and improved AWS CDK construct for Amazon DynamoDB tables](https://aws-oss.beachgeek.co.uk/3m7) looks at the reasoning behind the creation of a new L2 construct for DynamoDB tables, as well as some of the features and how to implement them [hands on]
* [Announcing Generative AI CDK Constructs](https://aws-oss.beachgeek.co.uk/3m8) explores the Generative AI CDK Constructs, an open-source extension of the AWS Cloud Development Kit (AWS CDK), that provides well-architected multi-service patterns to quickly and efficiently create repeatable infrastructure that includes five CDK constructs enabling key generative AI capabilities like question and answering, summarisation, data ingestion for Retrieval Augmented Generation (RAG), and model deployment capabilities [hands on]
* [Upgrade to Amazon Aurora MySQL version 3 (with MySQL 8.0 compatibility)](https://aws-oss.beachgeek.co.uk/3mc) discusses a framework to prepare you for your MySQL upgrade, diving into the upgrade process [hands on]
* [Build preview environments for Amazon ECS applications with AWS Copilot](https://aws-oss.beachgeek.co.uk/3md) walks you through a step by step guide on how to build preview environments using AWS Copilot in GitLab [hands on]
* [Invoking on-premises resources interactively using AWS Step Functions and MQTT](https://aws-oss.beachgeek.co.uk/3me) demonstrates how to use the MQTT protocol (AWS IoT Core) with AWS Step Functions to dispatch jobs to on-premises workers to access or retrieve data stored on-premises [hands on]

![invoking on-premises resources using MQTT and AWS Step Functions architecture overview](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/01/29/sfn-mqtt1.png)

### Quick updates

**Powertools for Lambda**

There were a couple of great updates last week for fans and users of Powertools for Lambda.

First up is Heitor Lessa who shared this [tweet](https://twitter.com/heitor_lessa/status/1753121423076262302?s=43&t=H9KFV1Y7tYStznH9fbvgFw) (with screen shot) on how Powertools for AWS partnered with the AWS Crypto team to make data confidentiality and integrity more accessible. That is a massive win, so great news.

The second update from Heitor was news that Powertools for Lambda now has a dedicated website. Head on over to [powertools.aws.dev](https://aws-oss.beachgeek.co.uk/3lw) for all your Powertools on Lambda needs!

 **OpenZFS**
 
Amazon FSx for OpenZFS, a service that provides fully managed file storage powered by the popular OpenZFS file system, now provides 14% higher levels of I/O operations per second (IOPS) at no additional cost, bringing the new maximum IOPS level to 400,000. The increased IOPS levels enable you to improve price–performance for IOPS-intensive workloads like Oracle databases and optimise costs for workloads like periodic reporting jobs with IOPS requirements that vary over time. Check the [announcement page](https://aws-oss.beachgeek.co.uk/3ly) for details around AWS region availability for this update.

In other OpenZFS news, Noor Fairoza and Daniel Whitehead have also written [Boosting Unreal Engine Performance with Amazon FSx for OpenZFS as a Shared Derived Data Cache](https://aws-oss.beachgeek.co.uk/3ma) that provides a step-by-step guide to configure Amazon FSx for OpenZFS as a Derived Data Cache (DDC) for Unreal Engine [hands on]
 
 **PostgreSQL**
 
Trusted Language Extensions for PostgreSQL (pg_tle) is an open source development kit to help you build extensions written in a trusted language, such as PL/Rust, that run safely on PostgreSQL. pg_tle now supports new crates for PL/Rust such as croaring-rs and num-bigint, enabling you to build more of your extensions on RDS for PostgreSQL. PL/Rust, a PostgreSQL trusted procedural language, combines the performance and resource efficiency of compiled languages like C and provides memory safety so that an unprivileged user can run code in the database.

Rust crates extend functionality in PL/Rust to help support more use cases such as for analytics, search, and security applications. croaring-rs adds support for roaring bitmap, a data type that provides better compression and lower memory utilisation compared to conventional bitmaps. Roaring bitamps are used for applications that require high performance lookups with a high compression ratio, such as analytics and big data. The num-bigint crate adds precision handling for arbitrarily large sized integers, which is used for security and scientific applications.

Support for num-bigint and croaring-rs crates is available on database instances in Amazon RDS running PostgreSQL 16.1-R2 and higher, 15.5-R2 and higher, 14.10-R2 and higher, and 13.13-R2 and higher in all applicable AWS Regions.

Also announced last week was news that Amazon Aurora PostgreSQL-Compatible Edition now supports PostgreSQL major version 16 (16.1). PostgreSQL 16 adds support for SQL/JSON constructors and identity functions, more query types that can use parallelism, and the ‘pg_stat_io’ view that provides statistics on I/O usage.

**Ruby**

AWS SDK for Ruby V3 now supports RBS type signatures. RBS is a language to describe the structure of Ruby programs. Read more about this in the post from Matt Muller,[ Announcing RBS support for AWS SDK for Ruby V3](https://aws.amazon.com/blogs/developer/announcing-rbs-support-for-aws-sdk-for-ruby-v3/)

**Event Ruler**

Event Ruler is an open source project that provides a Java library that can match rules against events in near real-time against any traffic. Today, EventBridge matches more than 2.6 trillion events per month for over 1.5 million customers. By running on Open Source Ruler, EventBridge can now collaborate directly with the broader developer community and will actively contribute to building new and enhanced filtering capabilities that anyone can use through the Apache 2.0 License. 

Amazon EventBridge event matching now runs on Open Source Event Ruler v1.50, enabling advanced filtering capabilities such as combining anything-but filtering (matching anything except for the value) with suffix filtering (matching against characters at the end of a value), and equals-ignore-case filtering (matching against a string regardless of case). For example, you can now match against values that don’t end with a specific file type such as .png or .jpeg. You can also combine prefix filtering (matching against characters at the beginning of a value) and suffix filtering with equals-ignore-case filtering.

Amazon EventBridge Event Bus is a serverless event router that enables you to create scalable event-driven applications by routing events between your own applications, third-party SaaS applications, and AWS services. You can set up rules to determine where to send your data, allowing applications to react to changes in your data as they occur. 

### Videos of the week

**Cedar**

This is a fabulous talk from Emina Torlak that dives deep into Cedar and how it implements provable security. This is this weeks must watch video.

{{< youtube KC6rlcsHUVs >}}


**Writing OpenSearch Extensions in Python**

The Extensions SDK, a new experimental feature in OpenSearch 2.9, allows you to extend OpenSearch and independently scale workloads without impacting cluster availability. But did you know that this feature now allows you to write one of these Extensions in Python? No need to use Java, and there’s no JVM required, making it super easy to do. In this video, dB. will show you how to write a plugin, how to write an extension in Java, and then how to write an extension on Python. dB. also demystifys some of the lowest levels of OpenSearch internals, such as its binary transport protocol.

{{< youtube TZy7ViZbbHc >}}


**Empowering developers to switch between CI/CD systems**

Great video from AWS Hero Johannes Koch who takes a look at projen, an open source project that  lets you define an abstract CI/CD pipeline which can then be rendered / generate for different CI/CD tools.

{{< youtube EIZpsJZa0HM >}}



### Events for your diary

If you are planning any events in 2024, either virtual, in person, or hybrid, get in touch as I would love to share details of your event with readers. 

I recently found this GitHub repo, [open-source-events](https://aws-oss.beachgeek.co.uk/3jt) that is a curated set of open source events for 2024. Go check it out and see what 2024 is looking like.

**SOOCon 24**
**London, UK 7th and 8th February, 2024**

The State of Open Conference is back at the wonderful Brewery in the City of London, the perfect place to catch up with the many open source developers, enthusiasts, and hackers. You can view more at the site page, [SOOCon24](https://stateofopencon.com/)

**Cortex**
**Every other Thursday, next one 16th February**

The Cortex community call happens every two weeks on Thursday, alternating at 1200 UTC and 1700 UTC. You can check out the GitHub project for more details, go to the [Community Meetings](https://aws-oss.beachgeek.co.uk/2h5) section. The community calls keep a rolling doc of previous meetings, so you can catch up on the previous discussions. Check the [Cortex Community Meetings Notes](https://aws-oss.beachgeek.co.uk/2h6) for more info.

**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://aws-oss.beachgeek.co.uk/1az)

### Stay in touch with open source at AWS

Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) for more open source goodness.

One of the pieces of feedback I received in 2023 was to create a repo where all the projects featured in this newsletter are listed. Where I can hear you all ask? Well as you ask so nicely, you can meander over to[ newsletter-oss-projects](https://aws-oss.beachgeek.co.uk/3l8).

Made with ♥ from DevRel