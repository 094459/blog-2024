---
title: 'AWS open source newsletter #183'
date: '2024-01-08'
tags : [ oss-newsletter, aws open source,  Cedar, Project, Prometheus, Grafana, Kubernetes, Amazon EKS, Mage, OpenSearch, AWS CDK, eBPF, Istio, Kubecost, PostgreSQL, MySQL, MariaDB, ActiveMQ, Apache Airflow, MWAA, Apache Spark, Ray, AWS Amplify, Spring Boot, Amazon EMR, AWS Neuron, Apache Cassandra, OpenTelemetry, Amazon Linux, AWS ParallelCluster, RabbitMQ]
canonicalUrl : "https://community.aws/content/2YwBFs7C8pmCo65sL0ViMeBUk1U/aws-open-source-newsletter-183?lang=en"
---

## January 8th, 2024 - Instalment #183

Happy new year and welcome to the first edition of the AWS open source newsletter of 2024, number #183.  The big news for 2024 is the move from dev.to to community.aws as the "home" for the AWS open source newsletter, although it will still be posted on dev.to as well. Let me know what you think, community.aws has some top notch content that many readers might not be aware of.

As always, this week we start like other issues with a round up of some new projects for you to practice your four freedoms. We have a new message queuing library, an open source generative AI based developer chat tool, a serverless URL shortener, an Amazon S3 proxy, a nice tool that provides you with diff's when using AWS CDK, and more.

As it has been a few weeks since our last edition, this week we have a bigger collection of content from you. It was hard to select these as there were so many great posts, but I have done my best and this week we feature content that includes Cedar, Projen, Prometheus, Grafana, Kubernetes, Mage, OpenSearch, AWS CDK, eBPF, Istio, Kubecost, PostgreSQL, MySQL, MariaDB, ActiveMQ, Apache Airflow, Apache Spark, Ray, AWS Amplify, Spring Boot, Amazon EMR, AWS Neuron, Apache Cassandra, OpenTelemetry, Amazon Linux, AWS ParallelCluster, and RabbitMQ.

Before you dive into the newsletter, make sure you check out the important update next.

**Important Update**

If you are using MySQL 5.7 or PostgreSQL 11 on Amazon RDS, then make sure you take time to read [Your MySQL 5.7 and PostgreSQL 11 databases will be automatically enrolled into Amazon RDS Extended Support](https://aws-oss.beachgeek.co.uk/3ik)

**Feedback**

Please please please take 1 minute to [complete this short survey](https://www.pulse.aws/promotion/10NT4XZQ). 

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes: Brian Granger, James Eastham, Yuichi Watanabe, Furkan Gulsen,  Richard Fan, Zied Ben Tahar, Marco Gonzalez, Nowsath,  Ravindra Singh, Eka Ponkratova, Ricardo Ferreira, Phil Windley, Michael Tran, Alain Krok, Dinesh Sajwan,  Mikhail Shapirov, Elamaran Shanmugam, Tsahi Duek, Shahar Azulay, Sheetal Joshi, Mike Stefaniak, Praseeda Sathaye, Vijay Chintalapati, Karthik Chemudupati, Scott Chang, James Wenzel, Isha Dua, Jason Janiak, and Thomas Nguyen, Maciej Walkowia, George John, Ashok Srirama, Hemanth AVS, Leah Tucker, Sean Smith and Ryan Kilpadi

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution. The projects mentioned here do not represent any formal recommendation or endorsement, I am just sharing for greater awareness as I think they look useful and interesting!*

#### Tools

**dynamomq**

[dynamomq](https://aws-oss.beachgeek.co.uk/3j1) is a project from Yuichi Watanabe that provides a message queuing library that leverages the features of DynamoDB to achieve high scalability, reliability, and cost efficiency. Notably, its ability to dynamically edit message order and attributes enables flexible adaptation to application requirements. Compared to existing solutions, DynamoMQ offers ease of management for developers while providing the reliability of fully managed services like Amazon SQS. It also encompasses key functionalities expected from a message queue, such as concurrent processing with multiple goroutines, Dead Letter Queues, and ensuring FIFO (First In, First Out) order.

![dynamomq message state machine diagram](https://camo.githubusercontent.com/bf47b153faa9e9428dabb55de56be40d213e8bf3b918172dd52c745a66326edf/68747470733a2f2f6361636f6f2e636f6d2f6469616772616d732f446a6f413270534b6e6843676854594d2d39333833432e706e67)

**cumuli-aws-console-chat**

[cumuli-aws-console-chat](https://aws-oss.beachgeek.co.uk/3j2)  is an open source Chrome extension that provides similar functionality to Amazon Q. The Cumuli Chrome extension adds a side panel with LLM chat to all AWS pages, and lets you add screenshots of the console to your queries to get context-aware responses. It's similar to Amazon Q but uses GPT-4 Turbo with vision. Check out the repo that includes a demo video of it in action.

**golang-url-shortener**

[golang-url-shortener](https://aws-oss.beachgeek.co.uk/3j3) is a project that you can build from Furkan Gulsen that deploys a URL shortener service, built with Go and Hexagonal Architecture, leverages a serverless approach for efficient scalability and performance. It uses a variety of AWS services to provide a robust, maintainable, and highly available URL shortening service. Are URL Shortners the new todo app? Not sure but I really like the quality of the documentation of this project, and like I did last year with implementing a serverless web analytics solution, I am going to check this project out and see if it would be a good replacement for the tool I currently use, YOURLS. Check out the discussion on reddit [here](https://www.reddit.com/r/aws/comments/18nnfix/url_shortener_hexagonal_serverless_architecture/).

![architecture for serverless url shortner](https://github.com/Furkan-Gulsen/golang-url-shortener/blob/main/assets/system_design.png?raw=true)

**rust-s3-cdn**

[rust-s3-cdn](https://aws-oss.beachgeek.co.uk/3j4) provides a Least Recently Used (LRU) cached proxy for AWS S3 written in Rust. I actually had to look up [LRU](https://helpful.knobs-dials.com/index.php/Cache_and_proxy_notes#Least_Recently_Used_(LRU)) as this was a new term for me. The repo provides a couple of reasons why you might want to use this tool, as well as helping you be aware of caveats too.

**cdk-notifier**

[cdk-notifier](https://aws-oss.beachgeek.co.uk/3it) is a lightweight CLI tool to parse a CDK log file and post changes to pull request requests. Can be used to get more confidence on approving pull requests because reviewer will be aware of changes done to your environments. I am not sure whether this is an old tool, but I have only just found out about it thanks to the blog post from AWS Community Builder, Johannes Konings. He put together [Use cdk-notifier to compare changes in pull requests](https://aws-oss.beachgeek.co.uk/3iu) that explains in more details how this works and walks you through using it.

### Demos, Samples, Solutions and Workshops

**aws-clean-rooms-lab**

[aws-clean-rooms-lab ](https://aws-oss.beachgeek.co.uk/3j5)is a workshop from AWS Security Hero Richard Fan that  will walk you through the setup of AWS Clean Rooms so you can try its different features. Richard wrote about this repo in his write up [Start building my AWS Clean Rooms lab](https://aws-oss.beachgeek.co.uk/3j6), which you should read to help you get started. This is a work in progress, but there is still a lot of stuff to get stuck into so worth checking out if AWS Clean Rooms is something that you are exploring.

**youtube-video-summarizer-with-bedrock**

[youtube-video-summarizer-with-bedrock](https://aws-oss.beachgeek.co.uk/3j7) is a example project from Zied Ben Tahar that uses large language models to create a YouTube video summariser, allowing you to sift through You Tube videos and get an high level summary of them, allowing you to make better decisions as to whether you want to spend more time watching the video.  Zied has also put together a supporting blog post, [AI powered video summariser with Amazon Bedrock](https://aws-oss.beachgeek.co.uk/3j8) that provides everything you need to get this project up and running for yourself.

### AWS and Community blog posts

**The best from around the Community**

It is great to see that the community has been busy over the last few weeks putting together some really outstanding content. Starting 2024 we have AWS Community Builder Marco Gonzalez  who has put together a nice post that summarises how you can begin your open source contribution journey in his post, [How to contribute Open Source Communities](https://aws-oss.beachgeek.co.uk/3is). The post has a number of resources that you can check out, so if you have made a new years resolution around contributing upstream, why not start by reading this post and see if it helps you. AWS Community Builder Nowsath has put together [Setup Prometheus and Grafana with existing EKS Fargate cluster - Monitoring](https://aws-oss.beachgeek.co.uk/3iv) where he shares  the fundamental steps for configuring Prometheus and Grafana within the existing Amazon EKS Fargate cluster, along with the establishment of custom metrics. Sticking with Kubernetes, next up we have AWS Community Builder Ravindra Singh with a short post [Simplifying Context Configuration and Switching in Multiple Kubernetes Clusters](https://aws-oss.beachgeek.co.uk/3ix), where he lists a number of tools to help you manage this. I found this useful as I was not aware of most of these tools, and I plan to try them out. 

Next up we have Eka Ponkratova with [Moving Data with Mage on AWS ECS](https://aws-oss.beachgeek.co.uk/3iy), which looks at Mage an open-source data pipeline tool for transforming and integrating data, that is "a modern replacement for Airflow" - fighting talk! The post shows you how you can deploy Mage on Amazon ECS. Wrapping things up this week we have my colleague Ricardo Ferreira with [Introduction to OpenSearch Models](https://aws-oss.beachgeek.co.uk/3iz), with a series of posts that explores how you can use machine learning models (yup, including the latest generative kind) to  improve the search relevancy of your data. Make sure you check it out, as it is a great read.

**Cedar**

Cedar is an open source policy language and evaluation engine, that helps developers to decouple access control from application logic by expressing fine-grained permissions as easy-to-understand policies.  In [Two New Open Source Rust Crates Create Easier Cedar Policy Management](https://aws-oss.beachgeek.co.uk/3ir) Phil Windley explains how developers using the Cedar SDK can use two new open source Rust crates, cedar-local-agent and avp-local-agent, to reduce their development burden and ease policy management tasks. This weeks essential read.

**Projen**

When starting a new project, you rarely start from scratch, but more often use a scaffolding tool to generate a new project structure. Whilst it varies, you will end up with a  large amount of configuration is created on your behalf, and you get the ownership of those files. Projen is an open source project generator that helps developers to efficiently manage those project configuration files. Michael Tran, Alain Krok, and Dinesh Sajwan have come together to write, [Getting started with Projen and AWS CDK](https://aws-oss.beachgeek.co.uk/3iq) to share how you can get started, as well as looking at the pros and cons. [hands on]

**Kubernetes**

Over the past few weeks, there were a few Kubernetes that I thought were worth sharing. 

First up is the post, [Simplify integration of your Amazon EKS cluster with Amazon EKS Blueprints for CDK](https://aws-oss.beachgeek.co.uk/3ic) [hands on] where Mikhail Shapirov and Elamaran Shanmugam introduce the Amazon EKS Blueprints for CDK framework, looking at common usage scenarios, providing examples and sample code, and presenting available resources for full implementations. Essential reading IMHO.

From Blueprints to eBPF, another increasingly interesting technology that folks should be getting more familiar with. In [Empowering Kubernetes Observability with eBPF on Amazon EKS](https://aws-oss.beachgeek.co.uk/3id)[hands on], Tsahi Duek and Shahar Azulay cover what eBPF is, why it’s important, and what eBPF-based tools are available for you to get visibility into your Amazon EKS applications.

![an overview of ebf tools](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2023/12/13/caretta-1.gif)

In [A deep dive into simplified Amazon EKS access management controls](https://aws-oss.beachgeek.co.uk/3ie) [hands on], Sheetal Joshi and Mike Stefaniak walk you through a new way to grant AWS IAM principals access to all supported versions (v1.23 and beyond) of Amazon EKS clusters and Kubernetes objects directly through Amazon EKS APIs.

One of the most popular (well read) posts on the open source blog was getting started with Itsio, so it was good to see Praseeda Sathaye and Vijay Chintalapati put together, [Getting Started with Istio on Amazon EKS](https://aws-oss.beachgeek.co.uk/3if) [hands on] that provides essential reading. 

Following that we had [Deploying AWS Load Balancer Controller on Amazon EKS](https://aws-oss.beachgeek.co.uk/3ig)[hands on], where Karthik Chemudupati, Scott Chang, and James Wenzel look at how to automate the manual deployment aspects of AWS Load Balancer Controller for existing EKS clusters.

Finishing up this weeks Kubernetes round up is the post, [Validating Cost Data for Amazon EKS with Kubecost and AWS Cost Explorer](https://aws-oss.beachgeek.co.uk/3ih) from Isha Dua, Jason Janiak, and Thomas Nguyen who provide a hands on look at integrating Kubecost to get granular visibility into your Amazon EKS cluster costs, letting you aggregate costs by the majority of Kubernetes contexts, starting from the cluster level down to the container level.

![a look at kubecost dashboards](https://d2908q01vomqb2.cloudfront.net/77de68daecd823babbb58edb1c8e14d7106e83bb/2023/11/27/Kubecost-AWS-Cost-Explorer-1.png)

**Other posts and quick reads**

* [Best practices for scaling AWS CDK adoption within your organization](https://aws-oss.beachgeek.co.uk/3ii) is a super interesting read around how to maximise the benefits of infrastructure as code tools like AWS CDK, to empower your internal developers and increase deployment velocity whilst keeping things secure
* [Securely connect to Amazon RDS for PostgreSQL with AWS Session Manager and IAM authentication ](https://aws-oss.beachgeek.co.uk/3ij) looks at how to connect to RDS databases using IAM authentication and Session Manager with the remote port forwarding capability,  and how this compares to the traditional database connection mechanisms you might be using [hands on]
* [Connect to MySQL and MariaDB from Amazon Aurora and Amazon RDS for PostgreSQL using the mysql_fdw extension](https://aws-oss.beachgeek.co.uk/3im) demonstrates the steps involved in setting up and using the mysql_fdw PostgreSQL extension on Amazon RDS for PostgreSQL, enabling you to interact with your MySQL database data [hands on]
* [Supercharge your MySQL database on AWS](https://aws-oss.beachgeek.co.uk/3in) provides essential reading for those of you using MySQL, or perhaps interested in using MySQL
* [Introducing Amazon MQ cross-Region data replication for ActiveMQ brokers](https://aws-oss.beachgeek.co.uk/3il) explains how cross-Region data replication works in Amazon MQ, how to set up a cross-Region replica broker, and how to test and promote the replica broker [hands on]
* [Orchestrate Amazon EMR Serverless Spark jobs with Amazon MWAA, and data validation using Amazon Athena](https://aws-oss.beachgeek.co.uk/3io) looks at how you can use Amazon MWAA, EMR Serverless, and Athena to build a complete end-to-end data processing pipeline [hands on]
* [Building Reliable and Scalable Generative AI Infrastructure on AWS with Ray and Anyscale](https://aws-oss.beachgeek.co.uk/3ip) looks at some of the challenges implementing generative AI workloads introduces, and how open source tools like Ray, can help
* [What’s new in AWS Amplify: Features to Build and Scale Fullstack Apps](https://aws-oss.beachgeek.co.uk/3iw) is a nice summary of the recent updates and new features that developers can use with AWS Amplify to help them build Fullstack applications

### Quick updates
 
**Spring Cloud AWS**

Maciej Walkowiak [shared details](https://www.linkedin.com/posts/maciejwalkowiak_springboot-springcloud-springframework-activity-7139961682096709632-yJku/) for those of you using Spring Boot on AWS. [Releases 3.1.0 and 3.0.4](https://aws-oss.beachgeek.co.uk/3i5) have updates and changes that cover integrate with AWS services such as S3, SQS, DynamoDB, and Secrets Manager, as well as updates to core and maintenance updates. Go check it out.

**Amazon EMR**

Amazon EMR Release 7.0 ships with Amazon Linux 2023 and features Apache Spark 3.5 running on Amazon Corretto Release 17 (built on OpenJDK) by default. It supports the latest versions of Python 3.9, glibc 2.34, and enables you to ensure consistency of package versions and updates across your environment. The latest release ships with AWS SDK for Java 2.20.160, and upgrades to the latest versions for Apache Flink 1.18 and latest open table formats (Apache Iceberg 1.4.2, Apache Hudi 0.14 and Delta 3.0). With Amazon EMR Release 7.0 ships with new enhancements which allow you to automatically observe and monitor your clusters. You can choose to publish system metrics to Amazon CloudWatch, Amazon Managed Service for Prometheus or your self-managed Prometheus cluster, and analyse your metrics using CloudWatch dashboard, Amazon Managed Grafana, or through the APIs. Find out more about this by checking out the documentation [here](https://aws-oss.beachgeek.co.uk/3i6).

**Kubernetes**

We had a number of updates for Kubernetes users over the past few weeks.

* Amazon EKS announces the general availability of upgrade insights, a new feature that surfaces insights about issues that may impact your ability to successfully upgrade a cluster to newer versions of Kubernetes. Upgrade insights are built upon best practices learned by EKS over the course of managing hundreds of thousands of Kubernetes clusters. You can use the EKS APIs and Console to check for upgrade readiness issues detected in your environment at any time against all future Kubernetes versions supported by EKS.
* Amazon Elastic Kubernetes Service (EKS) now surfaces cluster-related health issues in the EKS console and API, providing administrators enhanced visibility into the health of their clusters. Cluster health status information helps customers to quickly diagnose, troubleshoot, and remedy issues with their clusters, enabling them to run more up-to-date and secure application environments.
* Amazon EKS customers can now leverage EC2 security groups to secure applications in clusters using Internet Protocol version 6(IPv6) address space. Amazon EKS supports IPv6 enabling customers to scale containerised applications on Kubernetes beyond limits of private IPv4 address space. Kubernetes cluster administrators often have to operate in environments where IPv6 and IPv4 networks coexist. Until today, they could use network security rules that span pod to pod and pod to external Amazon Web Services service traffic defined in a single place with EC2 security groups, and applied to individual pods in IPv4 clusters. With this launch, customers can apply EC2 security groups for pods in both IPv4 and IPv6 clusters.
* Amazon EKS now supports simplified configuration of AWS Identity and Access Management (IAM) users and roles with Kubernetes clusters, through a new set of APIs that tightly integrate IAM identities with Kubernetes authentication and authorisation controls. EKS already supports IAM identity authentication to Kubernetes clusters, removing the burden from cluster administrators of having to maintain and integrate a separate identity provider. This integration enables administrators to leverage IAM security features such as audit logging and multi-factor authentication. EKS access management controls introduced today simplify the process of mapping IAM to Kubernetes identities, by allowing administrators to fully define authorised IAM principals and their associated Kubernetes permissions directly through an EKS API during or after cluster creation. The IAM identity used to create a EKS cluster can have its Kubernetes permissions removed or scoped down to comply with security requirements, and control of a cluster can always be restored to an AWS account administrator. Other AWS services can use EKS access management controls to automatically obtain permissions to run applications on EKS clusters. EKS access management controls simplify the amount of work administrators need to do in order to create and manage clusters that are shared by multiple users and other AWS services. Dive deeper by reading this post, [Amazon EKS Pod Identity: a new way for applications on EKS to obtain IAM credentials](https://aws-oss.beachgeek.co.uk/3i7) where George John, Ashok Srirama, and Hemanth AVS show you how you can use the Amazon EKS Pod Identity feature to securely grant IAM permissions to Kubernetes applications running in your EKS clusters.

![overview of amazon eks and iam](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2023/12/20/Pod-Identity-Worklow.jpg)

Finally, if you were not aware, there is a new Amazon EKS Developers workshop that provides a comprehensive and beginner-friendly workshop designed specifically for developers embarking on their Kubernetes and Amazon Elastic Kubernetes Service (Amazon EKS) journey. Find out more about this workshop by checking out the post,[ Discover application refactoring with the EKS Developers Workshop](https://aws-oss.beachgeek.co.uk/3i9), where Leah Tucker walks you through the workshop and provides links so you can get started.

**AWS Neuron**

AWS Neuron is the SDK for Amazon EC2 Inferentia and Trainium based instances purpose-built for generative AI. With the Neuron 2.16 release, we now support Llama-2 70b model inference on Inf2 instances.  Neuron integrates with popular ML frameworks like PyTorch and TensorFlow, so you can get started with minimal code changes and without vendor-specific solutions. Neuron includes a compiler, runtime, tools, and libraries to support high performance training and inference of generative AI models on Trn1 instances and Inf2 instances. 

Neuron 2.16 adds inference support for Llama-2 70b and Mistral-7b models with Transformers NeuronX. This release includes support for PyTorch 2.1 (beta) and Amazon Linux 2023. Neuron 2.16 improves LLM model training user experience with PyTorch Lightning Trainer (beta) support. PyTorch inference now allows to dynamically swap different fine-tuned weights for loaded models. This release introduces Neuron Distributed Event Tracing (NDET) tool to improve debuggability and profiling collective communication operators in the Neuron Profiler tool.

**PostgreSQL**

There was a lot of stuff to catch up over the last few weeks, so here is a summary of the important bits:

* *Amazon Aurora for PostgreSQL now supports h3-pg for geospatial indexing* - Amazon Aurora PostgreSQL-Compatible Edition now supports the h3-pg extension, which provides an API to H3, an open-source hexagonal, hierarchical geospatial indexing system. With this extension, you can perform different kinds of spatial analysis over large datasets, including efficient indexing and lookups, modelling flow through a grid, and applying machine learning models over your geospatial data stored in Aurora PostgreSQL. The H3 library provides an invariant set of hexagonal map tiles over multiple layers of resolution. This allows the h3-pg extension to index your geospatial data so you can efficiently query data on your maps. For example, a retailer planning new outlets may want to create a heatmap visualisation using traffic, mobility, demographic, and other geospatial datasets to identify locations best suited for their customers. You can also use H3 and PostGIS together to perform different geospatial analyses. The h3-pg extension is available on Aurora PostgreSQL 15.5, 14.10, 13.13, 12.17 and higher.
* *Amazon Aurora PostgreSQL now supports HypoPG extension for creating hypothetical indexes* - Amazon Aurora PostgreSQL-Compatible Edition now supports the HypoPG extension for creating hypothetical indexes, which lets you test the performance impact of an index on query plans before you build it. Indexes are a way to accelerate queries in PostgreSQL, however, building indexes in a production system requires additional storage and may not necessarily improve the performance of slow-running queries. The HypoPG extension lets you test the impact of adding an index without having to build it, and lets you determine if you should build an index before using CPU and storage resources. HypoPG helps to provide you insight into whether the PostgreSQL query planner will choose to use an index and any performance benefits that result from the use of the index. The HypoPG extension is available on Aurora PostgreSQL 15.5, 14.10, 13.13, 12.17 and higher.
* *Amazon Aurora for PostgreSQL now supports delegating extension management to lower privileged users* - Amazon Aurora PostgreSQL-Compatible Edition now supports the rds_extension database role which provides a cluster administrator the ability to delegate create, alter, or drop extension operations to lower privileged users. The cluster administrator can use the new rds.allowed_delegated_extensions DB parameter to limit which extensions a member of the rds_extension role can manage. To get started, take a look at our Working with extensions and foreign data wrappers page. Delegation of extension management using the rds_extension role is available on Aurora PostgreSQL 15.5, 14.10, 13.13, 12.17
* *Amazon Aurora supports PostgreSQL 15.5, 14.10, 13.13, 12.17* - Amazon Aurora PostgreSQL-Compatible Edition now supports PostgreSQL versions 15.5, 14.10, 13.13, 12.17. These releases contain product improvements and bug fixes made by the PostgreSQL community, along with Aurora-specific improvements. This release also contains new features and improvements such as group role authentication support using AWS Directory Service for Microsoft Active Directory with the new pg_ad_mapping extension, Amazon Bedrock integration for Generative AI , and Babelfish for Aurora PostgreSQL version 3.4. As a reminder, if you are running any version of Amazon Aurora. PostgreSQL 11, you must upgrade to a newer major version by February 29, 2024.

**MySQL and MariaDB**

Amazon Relational Database Service (Amazon RDS) for MariaDB now supports MariaDB minor versions 10.11.6, 10.6.16, 10.5.23, and 10.4.32. We recommend that you upgrade to the latest minor versions to fix known security vulnerabilities in prior versions of MariaDB, and to benefit from the bug fixes, performance improvements, and new functionality added by the MariaDB community.

**Apache Cassandra**

Amazon Keyspaces (for Apache Cassandra) is a scalable, serverless, highly available, and fully managed Apache Cassandra-compatible database service that offers 99.999% availability. Today, Amazon Keyspaces added query auditing support for Keyspaces Data Manipulation Language (DML) operations with AWS CloudTrail.  With DML auditing, you can set up auditing for database operations such as INSERT, UPDATE, SELECT, DELETE, and more. You can now quickly determine which rows were created, read, updated, or deleted and identify the source of the calls. For robust monitoring and alerting, you can also integrate AWS CloudTrail events with Amazon CloudWatch Logs. You can also use AWS CloudTrail advanced event selectors for more granular control of which DML events you want to log from Amazon Keyspaces. 

**OpenTelemetry**

Amazon CloudWatch announces support for the OpenTelemetry Protocol (OTLP) 1.0.0 specification as a new output format in CloudWatch Metric Streams. With Metric Streams, you can create a continuous, near real-time stream of metrics to a destination of your choice. You can use Metric Streams to send metrics to your data lake on Amazon Web Services (AWS), such as Amazon Simple Storage Service (Amazon S3), or to other destinations including AWS Partner solutions. Now customers can output using OTLP 1.0.0 specification, in addition to the existing output formats of JSON and OTLP 0.7.0 in Metric Streams.

**AWS Amplify**

AWS Amplify now supports using existing MySQL and PostgreSQL databases for GraphQL APIs created with Amplify’s Cloud Development Kit (CDK) construct, enabling you to create a backend-for-frontend API layer for web and mobile apps with ease. Developers often have data spread across various databases and sources. With Amplify's new feature, you can now leverage your existing relational data for GraphQL APIs in addition to Amazon DynamoDB.

Creating a new GraphQL API for existing MySQL and PostgreSQL data sources can be a manual and tedious process, requiring developers to hand-author the API logic, configure networking settings between the API and database layer, and spend hours reflecting changes to the database schema back to the API. The Amplify workflow only takes three steps. First, provide your database endpoint to let Amplify generate a GraphQL API with CRUD operations and, optionally, configure necessary VPC settings. Second, enhance the GraphQL API using “directives” to configure additional authorisation rules (“@auth”) and relational queries (“@hasOne”, “@hasMany”). Finally, as your use cases evolves, Amplify allows you to create custom queries and mutations using a new “@sql” directive.

Check out the supporting blog post from my colleague Channy, [New for AWS Amplify – Query MySQL and PostgreSQL database for AWS CDK](https://aws-oss.beachgeek.co.uk/3i8)

**Amazon Linux**

A couple of Amazon Linux related updates that are important to be aware of.

* *AWS CloudShell has migrated to Amazon Linux 2023 (AL2023)* - AWS CloudShell, previously based on Amazon Linux 2 (AL2), has migrated to Amazon Linux 2023 (AL2023). You can continue to use your existing CloudShell environment with all its pre-installed tools.
* *Amazon Linux announces support for KVM and VMWare images with AL2023.3* - Announced at the end of 2023, Amazon Linux 2023 images for KVM and VMWare are now available,  with the third quarterly update. Customers can run Amazon Linux 2023 (AL2023) as a virtualised guest outside of directly being run on Amazon EC2. There are currently KVM (qcow2) and VMware (OVA) images available. These images for KVM and VMware hypervisor environments helps customers migrate their workloads to AL2023. This also allows customers to standardise on a single operating system across their on-prem and cloud environments. AL2023.3 also introduces some new packages like libreswan, NodeJS20, and Boto3. Libreswan is an implementation of the Internet Key Exchange (IKE) protocol and is used to establish IPsec tunnels. It supports versions 1 and 2 of IKE, and is an update to the same IKE implementation previously shipped with AL2. NodeJS 20 is the latest LTS release of the NodeJS JavaScript runtime environment. Boto3 is the official AWS SDK for Python. 
* *AWS Cloud9 now supports Amazon Linux 2023* - You can now launch AWS Cloud9 environments with Amazon Linux 2023 (AL2023). AL2023 is the next generation of Amazon Linux, a Linux server operating system from Amazon Web Services (AWS). AL2023 provides a secure, stable, and high performance execution environment to develop and run cloud and enterprise applications.

**Python**

AWS Lambda now supports creating serverless applications using Python 3.12. Developers can use Python 3.12 as both a managed runtime and a container base image, and AWS will automatically apply updates as they become available. You can use Python 3.12 with Lambda@Edge, allowing you to customise low-latency content delivered through Amazon CloudFront. Powertools for AWS Lambda (Python), a developer toolkit to implement serverless best practices and increase developer velocity, also supports Python 3.12. 

The Lambda Python 3.12 runtime is built on the new Amazon Linux 2023 runtime, which provides a significantly smaller deployment footprint than earlier Amazon Linux 2-based runtimes, updated versions of common libraries such as glibc, and a new package manager. The runtime also includes improved Unicode handling and support for graceful shutdown. For more information, see our blog post at Python 3.12 runtime now available in AWS Lambda.

Check out the supporting blog post, [Python 3.12 runtime now available in AWS Lambda](https://aws-oss.beachgeek.co.uk/3ia)

**AWS ParallelCluster**

AWS ParallelCluster 3.8 is now generally available. Key features in this release are support for Rocky Linux 8 and Amazon EC2 Capacity Blocks for ML, allowing you to reserve highly sought-after GPU instances on a future date to support your short duration machine learning (ML) workloads. Other important features in this release include:

* Scaling strategies to help you meet your scaling and cost requirements, ranging from strict all-or-nothing, that avoid launching idle instances, to best-effort, which prioritises throughput scaling over avoiding idle instances.
* Support for mounting user-defined file systems in AWS to the /home directory of the head node, helping you simplify cluster storage management. 
* Custom Munge key to help you simplify integration of additional cluster resources that require the Scheduler Munge key.

On an unrelated note, in case you missed this over the holiday period, Sean Smith and Ryan Kilpadi put together [Slurm REST API in AWS ParallelCluster](https://aws-oss.beachgeek.co.uk/3ib), showing you how you can setup the Slurm REST API that allows you to programmatically control your cluster,  making it possible to build the cluster into an automated workflow. 

![overview of Slurm REST API post architecture](https://d2908q01vomqb2.cloudfront.net/e6c3dd630428fd54834172b8fd2735fed9416da4/2023/11/27/CleanShot-2023-11-27-at-13.37.39.png)

**RabbitMQ**

Amazon MQ now provides support for RabbitMQ version 3.10.25, which includes several fixes and performance improvements to the previous versions of RabbitMQ supported by Amazon MQ. If you are running earlier versions of RabbitMQ, such as 3.10, 3.9 or 3.8, we strongly encourage you to upgrade to RabbitMQ 3.10.20 or higher. This can be accomplished with just a few clicks in the AWS Management Console. We also encourage you to enable automatic minor version upgrades on RabbitMQ 3.10.25 to help ensure your brokers take advantage of future fixes and improvements.

### Videos of the week

**Accelerating AI/ML Development with Open Source Software**

Brian Granger's keynote at the Cassandra Summit explored our two fold strategy around open source software in AI/ML. First, AWS has built products that bring the innovation and value of open source software to customers, with a focus on making it easy for them to configure, deploy, operate and use open source software on AWS in a manner that is secure, reliable, and cost efficient. Second, AWS is participating in and contributing to open source software that customers care about, to ensure that software is sustainable, stable, and continually innovating. In this keynote, he shares three key open source projects in the AI/ML space and how we are working with them to make sure that our customers have the tools to accelerate their development with confidence.

{{< youtube qKuqxM2O55s >}}

**Deploy a SpringBoot 3 API on AWS Lambda in 10 minutes**

James Eastham is back with another video where he dives into deploying  a brand new SpringBoot 3 API on AWS Lambda in under 10 minutes. James also then explores how to use Lambda SnapStart to improve the performance of your SpringBoot Lambda functions at startup.


{{< youtube HQQD4dndDpE >}}

# Events for your diary

If you are planning any events in 2023, either virtual, in person, or hybrid, get in touch as I would love to share details of your event with readers. 

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

### Stay in touch with open source at AWS

Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) for more open source goodness.

