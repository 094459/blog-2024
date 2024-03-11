---
title: 'AWS open source newsletter #192'
date: '2024-03-11'
tags : [ oss-newsletter, aws open source, AWS CDK, OpenSearch, Airbyte, PySpark, Jupyter, PostgreSQL, Dash, AWS SAM, Bref, Amazon EKS, Kubernetes, Apache Airflow, LocalStack, Cedar, Spring Boot, Amazon Corretto,  AWS Distro for OpenTelemetry, Prometheus, MySQL, Amazon Linux 2023, RabbitMQ, Credentials Fetcher, Istio]
canonicalUrl: "https://community.aws/content/2dXKq2lcjZmZlWHVBUIXoicPbrG/aws-open-source-newsletter-192"
---

##  Edition #192

Welcome to issue #192 of the AWS open source newsletter, the newsletter where we try and provide you the best open source on AWS content.  As always, this week we start with a round up of some freshly baked new projects for you to practice your four freedoms. A wide variety this week, and we have projects that help you create architecture diagrams from your YAML, visualise and create dashboards for compliance and reporting purposes, a new multi-cloud threat detection tool, a Go implementation of Cedar, an example of load testing your large language models, and more! 

For the readers out there, we have plenty to keep you busy with posts covering open source projects such as AWS CDK, OpenSearch, Airbyte, PySpark, Jupyter, PostgreSQL, Dash, AWS SAM, Bref, Kubernetes, Apache Airflow, LocalStack, Cedar, Spring Boot, AWS Distro for OpenTelemetry, Prometheus, MySQL, Amazon Linux 2023, RabbitMQ, Credentials Fetcher, and Istio. As always, don't skip the end of the newsletter, where we feature open source events and meet ups that you need to know about. Speaking of which....

**OpenSearchCon Call for Papers**

OpenSearchCon Europe is happening on May 6th and 7th at Cafe Moskau in Berlin, Germany (see Events section). The Call for Papers is open until March 25th, so you still have plenty of time to submit a talk for the event. Read more about the event below, and check out the [Call for Papers link here](https://aws-oss.beachgeek.co.uk/3pm).

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution. The projects mentioned here do not represent any formal recommendation or endorsement, I am just sharing for greater awareness as I think they look useful and interesting!*

### Tools

**diagram-as-code**

[diagram-as-code](https://aws-oss.beachgeek.co.uk/3ql) is a command line interface (CLI) tool enables drawing infrastructure diagrams for Amazon Web Services through YAML code. It facilitates diagram-as-code without relying on image libraries. The CLI tool promotes code reuse, testing, integration, and automating the diagramming process. It allows managing diagrams with Git by writing human-readable YAML. The README provides an example diagram (and the source that this tool used to generate it).

**CloudGrappler**

[CloudGrappler](https://aws-oss.beachgeek.co.uk/3qb) is a purpose-built tool designed for effortless querying of high-fidelity and single-event detections related to well-known threat actors in AWS. Andi Ahmeti has put together a blog post, [Introducing CloudGrappler: A Powerful Open-Source Threat Detection Tool for Cloud Environments](https://aws-oss.beachgeek.co.uk/3qc), that provides an overview of how this works with examples.

**powerpipe**

[powerpipe](https://aws-oss.beachgeek.co.uk/3qd) is dashboards and benchmarks as code. Use it to visualise any data source, and run compliance benchmarks and controls, for effective decision-making and ongoing compliance monitoring. As with all the Turbot open source projects, excellent documentation, and they have included a video that provides a demo of this at work.

{{< youtube -h6RSpvR0FE >}}

**language-server-runtimes**

[language-server-runtimes](https://aws-oss.beachgeek.co.uk/3qe) is a JSON-RPC based protocol for interactions between servers and clients (typically embedded in development tools). The README covers details around specification support and features supported, that will help you tailor this to your needs.

![uml flow of langauge server runtimes](https://github.com/aws/language-server-runtimes/blob/main/flow-diagram.png?raw=true)

**cedar-go**

[cedar-go](https://aws-oss.beachgeek.co.uk/3qf) provides the Go implementation of the Cedar policy language. Check out the README for a quick example of how to use Cedar within your Go applications, and am looking forward to seeing how Go developers start to incorporate this into their applications.

**load-test-llm-with-locust**

[load-test-llm-with-locust](https://aws-oss.beachgeek.co.uk/3qg) provides an example of how to perform load testing on the LLM API to evaluate your production requirements. The code is developed within a SageMaker Notebook and utilises the command line interface to conduct load testing on both the SageMaker and Bedrock LLM API. If you are not familiar with Locust, it is an open source load testing tool, and is a popular framework for load testing HTTP and other protocols. Its developer friendly approach lets you to define your tests in regular Python code. Locust tests can be run from command line or using its web-based UI. Throughput, response times and errors can be viewed in real time and/or exported for later analysis.

### Demos, Samples, Solutions and Workshops

**song-identification-on-aws**

[song-identification-on-aws](https://aws-oss.beachgeek.co.uk/3qj) This repo contains sample code that demonstrates how you can "fingerprint" your songs, and then detect the presence of your songs in either stored audio files like MP3s, or within streaming media. The underlying idea is to convert audio data into a spectrogram, and then isolate important markers within the spectrogram that will allow us to identify music. Roughly 10000 to 25000 fingerprints will be created for an average length song. Each fingerprint is stored as a large integer. See the blog post for more details about how the system works.

![overview of song identification architecture](https://github.com/aws-samples/song-identification-on-aws/blob/main/architecture.png?raw=true)

**public-file-browser-for-amazon-s3**

[public-file-browser-for-amazon-s3](https://aws-oss.beachgeek.co.uk/3qk) allows customers to create a simple PUBLIC file repository using Amazon S3 and Amazon CloudFront. This sample code deploys a website and a public files S3 bucket which can be loaded with any files they wish to publish publicly online.

![overview of the web ui](https://github.com/aws-samples/public-file-browser-for-amazon-s3/blob/main/docs/home-screenshot-3.png?raw=true)

![architecture overview of how this works](https://github.com/aws-samples/public-file-browser-for-amazon-s3/blob/main/docs/arch-overview.png?raw=true)


### AWS and Community blog posts

Each week I spent a lot of time reading posts from across the AWS community on open source topics. In this section I share what personally caught my eye and interest, and  I hope that many of you will also find them interesting. 

**The best from around the Community**

We have another great selection of community sourced open source content for you this week, and starting us off this week is AWS Community Builder Dakota Lewallen who has put together a short post on his thoughts on how to organise and approach creating your AWS CDK resources. This post has made me think about my own use of AWS CDK, so why not check it out yourself by diving into [Organize Your CDK lib Folder by Function Not Service](https://aws-oss.beachgeek.co.uk/3q1). Sticking with AWS CDK, and adding a sprinkling of OpenSearch, we have AWS Community Builder Peter McAree who has put together [Optimising your OpenSearch Ingestion pipeline using AWS CDK](https://aws-oss.beachgeek.co.uk/3q3), where he shows you how you can  leverage EventBridge Scheduler to optimise your OpenSearch Ingestion pipeline costs. 

Airbyte is an open source Extract, Load, Transform (ELT) platform that enables the creation of data pipelines for data ingestion and replication from various sources to different destinations, and AWS Community Builder User avatar Anish Shilpakar has put together [Unleashing the power of ELT in AWS using Airbyte](https://aws-oss.beachgeek.co.uk/3q4), a tutorial where you'll learn how to connect Airbyte with your Amazon S3 data lake and perform ELT operations from a REST API. Stick with data, AWS Community Builder Mostefa Brougui shares a quick hands on guide on how you can encrypt and decrypt sensitive data columns using PySpark in a Jupyter Notebook in his post, [Enhancing Data Security with Spark: A Guide to Column-Level Encryption - Part 1](https://aws-oss.beachgeek.co.uk/3q5). Diving deep into PostgreSQL this week we have AWS Hero Franck Pachot who takes a closer look at PostgreSQL bloat and vacuum, providing a detailed explanation of what they are and how they work, in his post [Postgres dead tuple space reused without vacuum](https://aws-oss.beachgeek.co.uk/3q8).

We have a couple of programming language related posts this week. First up is AWS Community Builder Maurice Borgmeier who shows you how to deploy a Dash app in a Lambda Function behind an API Gateway in the post, [Deploying a Serverless Dash App with AWS SAM and Lambda](https://aws-oss.beachgeek.co.uk/3q6). Dash is a popular open source Python framework for building interactive frontend applications without writing a single line of Javascript. From Python to PHP, and AWS Community Builder Rafael Araújo who kicks of the first in a series of posts that demonstrate PHP serverless applications using Bref, in his post [A bref AWS PHP story – Part 1](https://aws-oss.beachgeek.co.uk/3q7).

To finish up this week we have a couple of cloud native posts. First up is AWS Community Builder Kondala Rao Patibandla who has put together [Automate Cluster Autoscaler in EKS](https://aws-oss.beachgeek.co.uk/3q9), that provides a hands on guide to show you how you can automate the process of creating and configuring Cluster Autoscaler and HPA in AWS Elastic Kubernetes Service (EKS). To close up this week, AWS Community Builder Eric Johnson helps you keep on top of your Kubernetes security in his post, [Auditing AWS EKS Pod Permissions](https://aws-oss.beachgeek.co.uk/3qa). Go check it out. 

**Apache Airflow**

Whilst not open source, I had to share this really cool project that has been put together by Kamen Sharlandjiev. Kamen has used PartyRock (a really cool generative AI playground that allows you to experiment, explore, and learn about how to use generative AI and large language models to do cool things) to help Apache Airflow developers. As regular readers will know, I have been doing a fair bit of work with Apache Airflow, so I am not a stranger when it comes to authoring workflows in Apache Airflow (or DAGs). Kamen has put together a tool that reviews your DAGs and make some recommendations. How cool is that? Way cool is what I thought, so why not try this out for yourself, go have a play over at the PartyRock page, [MWAA / Apache Airflow DAG Tuning Assistant](https://aws-oss.beachgeek.co.uk/3px)

**LocalStack**

If you have not heard of [LocalStack](https://aws-oss.beachgeek.co.uk/3pr) before, it is an open source tool that helps developers build and test applications locally, emulating AWS services locally. Sarath Krishnan, Waldemar Hummer, and Harsh Mishra have put together a post that demonstrates how you can use LocalStack on your developer machine to test your AWS CDK projects locally. Sound interesting? If so, you can go read [Accelerating software delivery using LocalStack Cloud Emulator from AWS Marketplace](https://aws-oss.beachgeek.co.uk/3ps) [hands on]

**Cedar**

This popped up on my socials last week, a scientific paper that takes a look at some of the performance characteristics of Cedar, that demonstrates how it was designed to scale. Check out this [tweet from Sarah Cecchetti](https://aws-oss.beachgeek.co.uk/3pz), and then grab a cup of your favourite beverage whilst you sit down to enjoy, [Cedar: A New Language for Expressive, Fast, Safe, and Analyzable Authorization](https://aws-oss.beachgeek.co.uk/3q0)

**Other posts and quick reads**

* [Petabyte-scale log analytics with Amazon S3, Amazon OpenSearch Service, and Amazon OpenSearch Ingestion](https://aws-oss.beachgeek.co.uk/3pq) looks at solutions that enable petabyte-scale log analytics using OpenSearch Service in a modern data architecture [hands on]
* [Using CRaC to reduce Java startup times on Amazon EKS](https://aws-oss.beachgeek.co.uk/3pt) provides a great overview of the impact of Coordinated Restore at Checkpoint (CRaC) on the startup time of a Spring Boot application running on Amazon EKS [hands on]

![overview of CraC in a CI/CD pipeline](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2024/03/05/implementation-storage-backends..png)

* [Automating Amazon EC2 Instances Monitoring with Prometheus EC2 Service Discovery and AWS Distro for OpenTelemetry](https://aws-oss.beachgeek.co.uk/3pu) demonstrates how you can use EC2 service discovery with AWS Distro for OpenTelemetry (ADOT) collector in order to automatically identify targets for scraping Prometheus metrics from dynamic EC2 environments [hands on]

![solution overview of adot collector scraping](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2024/03/03/ec2_sd_diagram_archiecture-Simple-Scrape.drawio.png)

* [Implement advanced replication features with Amazon RDS for MySQL and Amazon Aurora MySQL using intermediate replication servers](https://aws-oss.beachgeek.co.uk/3pv) helps you understand how you can use advanced replication features between MySQL-compatible databases such as Amazon Aurora MySQL-Compatible Edition clusters or Amazon Relational Database Service (Amazon RDS) for MySQL instances [hands on]
* [Deploy Next.js 14 SSR apps with AWS Amplify Hosting’s Amazon Linux 2023 Support](https://aws-oss.beachgeek.co.uk/3pw) provides an overview of how to update your Amplify Hosting applications to use Amazon Linux 2023 as the build image [hands on]
* [Enhancing security in OpenSearch 2.12.0: The end of the default admin password](https://aws-oss.beachgeek.co.uk/3py) explains an important security related update that you should check out

### Quick updates

**ECS Compose-X**

Great news from AWS Community Builder John Preston, [ECS Compose-X 1.0.0](https://aws-oss.beachgeek.co.uk/3qh) was released over the weekend. If you are not familiar with [ECS Compose-X](https://aws-oss.beachgeek.co.uk/20s), it is an open source tool that helps you simplify how to deploy your applications and services onto Amazon ECS in a few simple steps. Go check it out if you have not already done so (and if you are coming to the AWS Summit London, John will be demoing this at the open source booth on the AWS Village)

**OpenSearch**

Last week saw the release of OpenSearch and OpenSearch Dashboards 1.3.15. You can read the full [release notes here](https://aws-oss.beachgeek.co.uk/3po).

Also announced last week was news that Amazon OpenSearch Serverless is enhancing access controls for VPC endpoints. With this feature, administrators can attach endpoint policies to control which AWS principals are allowed or denied access to the OpenSearch resources through their VPC endpoint(s). With a VPC endpoint policy, users can also combine actions along with AWS principals and resources to have finer control on the allowing or denying the traffic through their VPC endpoint(s).

**Kubernetes**

As of last week, you can now use private cluster endpoints with AWS Batch on Amazon Elastic Kubernetes Service (Amazon EKS). You can bring existing private Amazon EKS clusters and create a compute environment on AWS Batch. This setup enables Amazon EKS jobs to run private endpoints using AWS Batch. Previously, AWS Batch allowed only for public Amazon EKS clusters to run Amazon EKS workloads through AWS Batch. With this feature, you can now use private Amazon EKS cluster endpoints with AWS Batch. This unlocks key benefits for security-sensitive applications and leverage AWS Batch's managed job scheduling and provisioning without compromising security or compliance policies.

**RabbitMQ**

Amazon MQ now provides support for RabbitMQ version 3.11.28, which includes several fixes and performance improvements to the previous versions of RabbitMQ supported by Amazon MQ. If you are running earlier versions of RabbitMQ, such as 3.10, 3.9 or 3.8, we strongly encourage you to upgrade to RabbitMQ 3.11.28 or higher. This can be accomplished with just a few clicks in the AWS Management Console. We also encourage you to enable automatic minor version upgrades on RabbitMQ 3.11.28 to help ensure your brokers take advantage of future fixes and improvements.

**gMSA authentication for Linux**

Group Managed Service Account (gMSA) is a managed account that provides automatic password management, service principal name (SPN) management, and the ability to delegate management to administrators over multiple servers or instances. This allows multiple containers or resources to share an AD account without having to authenticate each container or resource individually, or without having access to network-shared resources such as SQL Server hosts, or file-shares. 

Amazon Elastic Container Service (ECS) now supports Group Managed Service Account (gMSA) for Linux containers running on AWS Fargate. With this support, applications running on AWS Fargate can easily authenticate with Microsoft Active Directory (AD) to access network shared resources. Until this update, customers could use gMSA with Amazon ECS Linux containers on EC2 using credentials-fetcher integration. Now, the same capability is available for containers running on AWS Fargate without having to manage servers or clusters of Amazon EC2 instances.

Cristobal Espinosa and Sai Kiran Akula have put together a post, [Windows authentication with gMSA on Linux containers on Amazon ECS with AWS Fargate](https://aws-oss.beachgeek.co.uk/3pp), with supporting code, that shows you how to use the integration of Credentials Fetcher with AWS Fargate on Amazon ECS.

![overview of architecture of gMSA authentication in Amazon ECS](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2024/02/18/AWS-Fargate.png)

### Videos of the week

**Istio Ambient Mesh - Ditch the Sidecar!**

Ram Vennam (solo.io) joins host Sai Vennam (AWS) to talk about Istio Service Mesh in Ambient Mode. With its sidecar-less approach, [Istio Ambient Mesh](https://aws-oss.beachgeek.co.uk/3pl) allows for simplified configuration and improved performance. After taking a look at the architecture, Sai and Ram walk you through a hands-on demo.

{{< youtube bbfiYMzHtH0 >}}

### Events for your diary

If you are planning any events in 2024, either virtual, in person, or hybrid, get in touch as I would love to share details of your event with readers. 

I recently found this GitHub repo, [open-source-events](https://aws-oss.beachgeek.co.uk/3jt) that is a curated set of open source events for 2024. Go check it out and see what 2024 is looking like.

**KubeCon / CloudNativeCon**
**Paris, 19th-22nd March**

Join AWS speakers at KubeCon Europe as they dive into the latest open source innovations innovations that make AWS the best place for customers to build and run open source software in the cloud. AWS conference speakers will be talking about Karpenter, Argo CD apps, the integration of AI in the CloudNative world, multi-tenant scalable Prometheus with Cortex, eBPF, Cloud Native CAKES stack for Zero Trust, chaos engineering, Kubernetes controllers, OpenTelemetry, and zonal outages. Don’t miss this opportunity to enhance your knowledge and connect with AWS experts.

Find out more by checking out the post from Chris Potter, [AWS at KubeCon + CloudNativeCon Europe 2024](https://aws-oss.beachgeek.co.uk/3pk)

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

So thank you to the following open source heroes: Andi Ahmeti, John Preston, Dakota Lewallen, Peter McAree, Jagadish Kumar, Muthu Pitchaimani, Sam Selvan, Cristobal Espinosa, Sai Kiran Akula, Ram Vennam, Sai Vennam, Chris Potter,  Islam Mahgoub, Raglin Anthony, Owen Hawkins, Sascha Moellering, Sarath Krishnan, Waldemar Hummer, Harsh Mishra, Jay Joshi, Shyam Sunder Rakhecha, Szymon Komendera, Neha Sharma, Matt Auerbach, Kamen Sharlandjiev, Darshit Chanpura, Kondala Rao Patibandla, Eric Johnson, Maurice Borgmeier, Rafael Araújo, Anish Shilpakar, Mostefa Brougui, and Franck Pachot.

**Feedback**

Please please please take 1 minute to [complete this short survey](https://www.pulse.aws/promotion/10NT4XZQ). 

### Stay in touch with open source at AWS

Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) for more open source goodness.

One of the pieces of feedback I received in 2023 was to create a repo where all the projects featured in this newsletter are listed. Where I can hear you all ask? Well as you ask so nicely, you can meander over to[ newsletter-oss-projects](https://aws-oss.beachgeek.co.uk/3l8).

Made with ♥ from DevRel