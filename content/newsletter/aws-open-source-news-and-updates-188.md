---
title: 'AWS open source newsletter #188'
date: '2024-02-12'
tags : [ oss-newsletter, aws open source, Cedar, Amazon EMR, Spring Boot, Amazon Corretto, Apache Zeppelin, Steampipe, ROS, Kubernetes, Amazon EKS, Apache Airflow, Prometheus, Grafana, Quarkus, Open Telemtry, Backstage, AWS CDK, MySQL, Redis, AWS ParallelCluster, OpenZFS, Karpenter, GraphQL]
canonicalUrl: "https://community.aws/content/2cG8daj0A3jo2DKBoE7x7NOw6aj/aws-open-source-newsletter-187"
---


##  Edition #188

Welcome to issue #188 of the AWS open source newsletter, the newsletter where we try and provide you the best open source on AWS content. 

As always, this week we start with a round up of some freshly baked new projects for you to practice your four freedoms. This week we have freshly cut repos that help you migrate your DNS configurations, improve your prompts when working with large language models, a new lightweight Javascript runtime, some reference code that shows you how you can deploy modern Java applications a number of different ways,  and sample repos that show you how you can do remote debugging in Amazon EMR, as well as the usual cool demos that showcase some of the ways you can use generative AI.

If that was not enough to satiate your open source needs, then why not dive into some of the posts we share this week, which include open source projects such as Cedar, Amazon EMR, Spring Boot, Apache Zeppelin, Steampipe, ROS, Kubernetes, Apache Airflow, Prometheus, Grafana, Quarkus, Open Telemtry, Backstage, AWS CDK, MySQL, Redis, AWS ParallelCluster, OpenZFS, Karpenter, and GraphQL.

Make sure you stick to the very end and check out the Events section at the end - and if you are running an open source event and want me to include it for broader visibility, please drop me a message at ricsue at amazon dot com.

**Feedback**

Please please please take 1 minute to [complete this short survey](https://www.pulse.aws/promotion/10NT4XZQ). 

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes: Vincent Mercier,  Dennis Kieselhorst, Yoanna Krasteva, Gianluigi Mucciolo,  Bob Tordella, Mike Likes Robots, Benjamen Pyle, Hein Htet Win, Jeroen Reijn, Michael Hausenblas, Michael Hicks, Damon Cortesi, Alexandre Magno Lima Martins, Riccardo Freschi, Adam Keller, Elamaran Shanmugam, Ratnopam Chakrabarti, Bhavye Sharma,  Benjamin Hodgens, Tom McDonald, Chelluru V N S S Vidyadhar, Steve Abraham, Abhay Saxena, Roberto Meda and William Lu.

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution. The projects mentioned here do not represent any formal recommendation or endorsement, I am just sharing for greater awareness as I think they look useful and interesting!*

### Tools

**llrt**

[llrt](https://aws-oss.beachgeek.co.uk/3mm) - Low Latency Runtime (LLRT) is a lightweight JavaScript runtime designed to address the growing demand for fast and efficient Serverless applications. LLRT offers up to over 10x faster startup and up to 2x overall lower cost compared to other JavaScript runtimes running on AWS Lambda. It's is built in Rust, utilising QuickJS as JavaScript engine, ensuring efficient memory usage and swift startup.

![performance benchmark matrix for llrt](https://github.com/awslabs/llrt/blob/main/benchmarks/llrt-ddb-put.png?raw=true)

**promptus**

[promptus](https://aws-oss.beachgeek.co.uk/3mu) Prompt engineering is key for generating high-quality AI content. But crafting effective prompts can be time-consuming and difficult. That's why Promptus was built. Promptus allows you to easily create, iterate, and organise prompts for generative AI models. With Promptus, you can:

* Quickly build prompts with an intuitive interface
* Automatically version and compare prompt iterations to optimise quality
* Organize prompts into projects and share with teammates
* See a history of your prompt and easily go back to any previous prompt execution

Whether you're an AI researcher, content creator, or business leader, Promptus gives you the power to unlock generative AI's full potential.

![example screenshot of promptus in action](https://github.com/aws-samples/promptus/blob/main/docs/images/promptusQExecuted.png?raw=true)

**prometheus-rds-exporter**

[prometheus-rds-exporter](https://aws-oss.beachgeek.co.uk/3mx) is a project from Vincent Mercier that provides a Prometheus exporter for AWS RDS. Check out the README, it is very detailed and well put together. It provides a lot of information on how they built this, examples of configurations as well as detailed configuration options. This looks very cool indeed, so nice work Vincent!

**bedrock-vscode-playground**

[bedrock-vscode-playground](https://aws-oss.beachgeek.co.uk/3nb) is a Visual Studio Code (VS Code) extension which allows developers to easily explore and experiment with large language models (LLMs) available in Amazon Bedrock. Check out the README for details of what you can do with it and how you can configure it to work with your specific setup.

![demo of bedrock vscode playground](https://github.com/awslabs/bedrock-vscode-playground/blob/main/media/openPlayground.gif?raw=true)

**route53-hostedzone-migrator**

[route53-hostedzone-migrator](https://aws-oss.beachgeek.co.uk/3nc) is a handy script will help you to automate the migration of an AWS Route 53 hosted zone from an AWS account to another one. It will follow all the needed steps published in the official AWS Route 53 documentation regarding the migration of a hosted zone.

**pinecone-db-construct**

[pinecone-db-construct](https://aws-oss.beachgeek.co.uk/3mn) The Pinecone DB Construct for AWS CDK is a JSII-constructed library that simplifies the creation and management of Pinecone indexes in your AWS infrastructure. It allows you to define, configure, and orchestrate your vector database resources alongside your AWS resources within your CDK application. The maintainer has shared some of the noteworthy features, which include:

* Handles CRUDs for both Pod and Serverless Spec indexes
* Deploy multiple indexes at the same time with isolated state management
* Adheres to AWS-defined removal policies (DESTROY, SNAPSHOT, etc.)
* Creates stack-scoped index names, to avoid name collisions

This is still in beta, so if you do try this out, please provide feedback to the maintainer.

**cedar-antlr-grammar**

[cedar-antlr-grammar](https://aws-oss.beachgeek.co.uk/3n0) - ANTLR (ANother Tool for Language Recognition) is a powerful parser generator for reading, processing, executing, or translating structured text or binary files. It's widely used to build languages, tools, and frameworks. From a grammar, ANTLR generates a parser that can build and walk parse trees. AWS Hero Ian Mckay has created one for Cedar.

**remote-debugging-with-emr**

[remote-debugging-with-emr](https://aws-oss.beachgeek.co.uk/3ne) is a Python-based CDK stack that deploys an EC2 bastion host and EMR Serverless and EMR on EKS environments configured for remote debugging.  Damon Cortesi takes a break from stacking/chopping logs to show you how to use this project that he wrote, using PyCharm with EMR on EKS and EMR Serverless to interactively debug your Spark applications. 

{{< youtube RhvuDeKvan8 >}}

### Demos, Samples, Solutions and Workshops

**bedrust**

[bedrust](https://aws-oss.beachgeek.co.uk/3n1) is a demo repo from my colleague Darko Mesaros that shows you how you can use Amazon Bedrock in your Rust code, and allows you to currently choose between Claude V2, Llama2 70B, and Cohere Command.

![screenshot of bedrust running](https://github.com/darko-mesaros/bedrust/blob/main/img/bedrust.png?raw=true)

**serverless-java-container**

[serverless-java-container](https://aws-oss.beachgeek.co.uk/3my) this repo provides a Java wrapper to run Spring, Spring Boot, Jersey, and other apps inside AWS Lambda. Serverless Java Container natively supports API Gateway's proxy integration models for requests and responses, you can create and inject custom models for methods that use custom mappings. Check out the supporting blog post from Dennis Kieselhorst, [Re-platforming Java applications using the updated AWS Serverless Java Container](https://aws-oss.beachgeek.co.uk/3mz). Very nice project!

**amazon-bedrock-voice-conversation**

[amazon-bedrock-voice-conversation](https://aws-oss.beachgeek.co.uk/3nd)  This repository provides a sample implementation of using Amazon Bedrock and other supporting AWS services to have a voice conversation with a Foundational AI model. The code demonstrates how to build an application with GenAI that supports natural back-and-forth voice conversations. This code serves as an example implementation for developers to reference when building voice-enabled applications powered by Foundational AI through Amazon Bedrock and related AWS services.

![architecture of bedrock voice conversation demo](https://github.com/aws-samples/amazon-bedrock-voice-conversation/blob/main/docs/amazon-bedrock-voice-conversation.png?raw=true)

**fargate-on-demand**

[fargate-on-demand](https://aws-oss.beachgeek.co.uk/3mv) this repo provides the code that shows you how you can cost optimise your container applications and then control scale down (or up) as needed. Yoanna Krasteva has put together a blog post that provides you with why and how you can configure this in the post, [Cost saving with AWS Fargate On-Demand](https://aws-oss.beachgeek.co.uk/3mw).

![architecture for fargate on demand](https://static.wixstatic.com/media/f1df0e_4854522dc74849598328e716054276ca~mv2.png/v1/fill/w_1480,h_692,al_c,q_90,usm_0.66_1.00_0.01,enc_auto/f1df0e_4854522dc74849598328e716054276ca~mv2.png)

### AWS and Community blog posts

Each week I spent a lot of time reading posts from across the AWS community on open source topics. In this section I share what personally caught my eye and interest, and  I hope that many of you will also find them interesting. 

**The best from around the Community**

I am not sure what the Community has been imbuing, but please share some with me, as there was some really top notch stuff produced last week,. To start this weeks choice selection, let's hear from AWS Community Builder Gianluigi Mucciolo who has written about Apache Zeppelin, an open source project that provides a web-based notebook that enables data-driven, interactive data analytics and collaborative documents with Python, Scala, SQL, Spark, and more. In [Serverless Apache Zeppelin on AWS](https://aws-oss.beachgeek.co.uk/3mo) Gianluigi walks you through a hands on guide on how to build a serverless infrastructure to run Apache Zeppelin and persist notebook files. Very nice post, so make sure you check it out. A name who should be familiar with regular readers of this newsletter, is Bob Tordella, who has been raising awareness and talking about Steampipe and how it can help you query hundreds of your AWS resource types from your AWS accounts using SQL. In [How to run an AWS CIS v3.0 assessment in CloudShell](https://aws-oss.beachgeek.co.uk/3mp) he does exactly what he says he will do, and shows you how you can run the latest AWS CIS benchmark (v3.0 in case you were curious) in AWS CloudShell. Check this out if you were not familiar with Steampipe, I think you will like. From Steampip to Steampunk, ok well maybe not quite but it's close enough. Mike Likes Robots is back again with more ROS content, in his post [ROS Control with the JetBot Part 1: Using I2C to control PWM](https://aws-oss.beachgeek.co.uk/3mq). Alexandre Magno Lima Martins has put together a great post that shares his experiences of running Apache Airflow in production on self managed, Amazon EKS. I learned some interesting things in this post, so rather than spoil it for you, why not dive right into [What we learned after running Airflow on Kubernetes for 2 years](https://aws-oss.beachgeek.co.uk/3n2). 

![graph of ramp up and ramp down airflow worker nodes on eks](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*BEmuO9olRrzT1yp7k-kRBQ.png)

One of the surprises from my time at Fosdem last week was the energy and interest in all things Observability, so it was good to see AWS Community Builder Benjamen Pyle put digital pen to digital papyrus in [Open Telemetry and Lambda](https://aws-oss.beachgeek.co.uk/3mr) where he provides an opinionated look at this topic, providing some good introduction material before diving into things. Check out the comments too. On a related note, Hein Htet Win has put together [Monitoring your AWS EKS Cluster with Managed Prometheus in AWS](https://aws-oss.beachgeek.co.uk/3ms) who shoes you how you can monitor your Amazon EKS cluster metrics in an agentless way. To conclude this weeks round up, we go to AWS Community Builder Jeroen Reijn has written [Analyze and debug Quarkus based AWS Lambda functions with X-Ray](https://aws-oss.beachgeek.co.uk/3mt) who takes you on an adventure on how Quarkus integrates with AWS X-Ray and how using a Jakarta CDI Interceptor can keep your code clean while adding custom instrumentation.

> **Do not miss this!** If you were not aware, my colleague Michael Hausenblas does a weekly newsletter on all things observability related. Make sure you subscribe to keep up with the excellent stuff he shares and writes about. You can find it at [https://o11y.news/](https://aws-oss.beachgeek.co.uk/99)

*(Note! I apologies if some of the words used are out of kilter to normal, I was listening to Janis Joplin and enjoying it a bit too much I think!)*

**Backstage**

Riccardo Freschi shares with you how to install and configure the Backstage add-on for Amazon EKS Blueprints in his post, [Building Developer Portals with Backstage and Amazon EKS Blueprints](https://aws-oss.beachgeek.co.uk/3n3). Backstage is an open source developer portal that has become very popular, and this post will give you a good start in how you can install and configure it for your needs.

![architecture for backstage on eks blueprints](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2024/02/07/backstage-diagram.png)

**AWS Cloud Development Kit (CDK)**

Big news last week for folks who have been using AWS CDK, with the general availability of CDK Migrate, a component of the AWS Cloud Development Kit (CDK). This feature enables users to migrate AWS CloudFormation templates, previously deployed CloudFormation stacks, or resources created outside of Infrastructure as Code (IaC) into a CDK application. You can dive deeper into this by checking out the post from Adam Keller, [Announcing CDK Migrate: A single command to migrate to the AWS CDK](https://aws-oss.beachgeek.co.uk/3n4).

**Other posts and quick reads**

* [Introducing multi-source replication on Amazon RDS for MySQL](https://aws-oss.beachgeek.co.uk/3n7) looks at multi-source replication on Amazon RDS for MySQL, its use cases, configuration best practices, and a walkthrough of an example use case [hands on]
* [Unlock on-demand, cost-optimized performance with Amazon ElastiCache Serverless](https://aws-oss.beachgeek.co.uk/3n9) helps you understand how to estimate ElastiCache Serverless for Redis costs in this new pay-per-use pricing model, and how to compare them to running workloads on alternative options
* [Configure Amazon EKS for environmental sustainability](https://aws-oss.beachgeek.co.uk/3n8) provides guidance on how to configure Amazon Elastic Kubernetes Service (Amazon EKS) for environmental sustainability,  through the lens of the Sustainability Pillar of the AWS Well-Architected Framework
* [Observing Kubernetes workloads on AWS Fargate with AWS managed open-source services](https://aws-oss.beachgeek.co.uk/3n5) explores leveraging the [AWS CDK Observability Accelerator](https://aws-oss.beachgeek.co.uk/31y) to build observability quickly for monitoring Amazon EKS on AWS Fargate with AWS-managed open-source services [hands on]

![architecture for open source observability for your kubernetes infr.](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2024/02/07/Picture1.jpg)

* [Improve application resiliency and performance with Multi-AZ Amazon FSx for OpenZFS](https://aws-oss.beachgeek.co.uk/3n6) demonstrates how you can increase their durability and availability using Amazon FSx for OpenZFS, all without any application modification [hands on]
* [Dynamic HPC budget control using a core-limit approach with AWS ParallelCluster](https://aws-oss.beachgeek.co.uk/3na) outlines a solution for managing your budget using a dynamic Amazon Elastic Compute Cloud (Amazon EC2) core allocation limit for each group asking for HPC resources [hands on]

### Quick updates

**Karpenter**

Starting with release of v0.34.0, Amazon Elastic Kubernetes Service (EKS) customers using the open-source Karpenter project have a new way to control how and when disruptive changes are made to the Amazon EC2 instances in their Kubernetes clusters. You can use Karpenter with EKS to help improve application availability, lower operational overhead, and increase cost-efficiency. Disruption controls offer deeper configuration for the automatic EC2 instance management capabilities of Karpenter so that you can fine-tune them for your specific needs and use cases.

Disruption controls give you more control over how Karpenter terminates EC2 instances to improve the balance between cost-efficiency, security, and application availability. In Karpenter’s NodePool configuration, you can now set disruption budgets for the EC2 instances provisioned by Karpenter, either as a percent or absolute value, to limit the impact to your application availability. These budgets can also be scheduled to only apply at certain times of the day, days of the week, or all the time so that you can further limit changes during critical business periods.

**GraphQL**

AWS AppSync is a managed service that connects applications to data. With AppSync, API developers can write resolvers and functions in JavaScript to define the business logic that connects their AppSync GraphQL and Pub/Sub APIs to data. AppSync now allows developers to define environment variables for their GraphQL API, making it easier to configure their code’s behaviour without having to change their resolver or function implementation. Developers can define key-value pairs on their GraphQL API at configuration time, and access them in their resolvers and functions at runtime when resolving GraphQL requests. Environment variables are available in JavaScript and VTL code. Developers can define environment variables on GraphQL APIs at creation time or in an update from the AWS AppSync console or with AWS CloudFormation, AWS Cloud Development Kit (CDK), the AWS CLI and the AWS SDKs.

### Videos of the week

**Cedar: A language for expressing fast, safe, and fine-grained authorization policies**

Michael Hicks presents this tutorial on Cedar, a new authorisation policy language developed as the core of AWS’s recently released Amazon Verified Permissions (AVP) service. Cedar policies are used to express fine-grained permissions on behalf of applications. Cedar was designed to be ergonomic, fast, safe, and analysable. Cedar’s simple and intuitive syntax supports common authorisation use-cases with easy-to-understand policies. Cedar’s policy structure ensures that access requests can be authorised quickly. Cedar is built using a high-assurance process we call verification-guided development. Its authorisation engine and validator are formally modelled in the Dafny programming language. Cedar’s core development team proves safety and security properties about those models in Dafny, and runs millions of automated differential tests to check that the implementations of the Cedar authorisation engine and validator, written in Rust, agree with the Dafny models

{{< youtube ttgfEun1NAM >}}

### Events for your diary

If you are planning any events in 2024, either virtual, in person, or hybrid, get in touch as I would love to share details of your event with readers. 

I recently found this GitHub repo, [open-source-events](https://aws-oss.beachgeek.co.uk/3jt) that is a curated set of open source events for 2024. Go check it out and see what 2024 is looking like.

**nor(DEV): Con**
**Feb 15-16th, Kings Centre, Norwich**

I will be speaking at nor(DEV):Con in Norwich, doing two talks. One will be on Apache Airflow (an entry level session, that is perfect if you have no clue about what Airflow is or does, but have heard a lot about it and want to take the first steps), and Cedar, an open source domain specific language that helps developers address the tricky subject of authorisation in their applications, allowing them to have a clean separation from business and authorisation logic.

Find out more about the event, the other sessions, at the event site, [nordevcon.com](https://aws-oss.beachgeek.co.uk/3ml)

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
