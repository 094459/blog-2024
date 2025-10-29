---
title: 'AWS open source newsletter #193'
date: '2024-03-18'
tags : [ oss-newsletter, aws open source, AWS Amplify, Kubernetes, Karpenter, NGNIX,  EKS-Anywhere, AWS CDK, Rust, OpenTelemetry, OpenSearch, Amazon Corretto, SnapStart, InfluxDB, Istio, Apache Flink, Apache Kafka, Prometheus, Trino, AWS ParallelCluster, MySQL]
canonicalUrl: "https://community.aws/content/2dr6KAMhu3PyxOrorgTq9apejEZ/aws-open-source-newsletter-193"
---

##  Edition #193

Welcome to issue #193 of the AWS open source newsletter, the newsletter where we try and provide you the best open source on AWS content.  Sadly I will be missing the fun at KubeCon in Paris, but if you are attending, make sure to check out the AWS booth - I had a sneak peak at what you can expect, and there is going to be some great demos being shown, a lot of our open source folk will be there.

As always, this week we start with a round up of some freshly baked new projects for you to practice your four freedoms. This week we have projects that provide controls over running EC2 instances, help you plan your costs for out of supported RDS database engines, a Rust based S3 file sharing utility, libraries to make working with Amazon Bedrock on .NET a breeze, and sample projects that this week include how to deploy Amazon API Gateway in multi-region active-passive deployment.

If that was not enough to keep you busy, then dive into the content created from the AWS Community on open source projects that this week include AWS Amplify, Kubernetes, Karpenter, NGNIX,  EKS-Anywhere, AWS CDK, Rust, OpenTelemetry, OpenSearch, Amazon Corretto, SnapStart, InfluxDB, Istio, Apache Flink, Apache Kafka, Prometheus, Trino, AWS ParallelCluster, and MySQL. 

**OpenSearchCon Call for Papers**

OpenSearchCon Europe is happening on May 6th and 7th at Cafe Moskau in Berlin, Germany (see Events section). The Call for Papers is open until March 25th, so you still have plenty of time to submit a talk for the event. Read more about the event below, and check out the [Call for Papers link here](https://pretalx.com/opensearchcon-europe-24/cfp).


### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution. The projects mentioned here do not represent any formal recommendation or endorsement, I am just sharing for greater awareness as I think they look useful and interesting!*

### Tools

**ec2RuntimeMonitor**

[ec2RuntimeMonitor](https://github.com/aws-samples/ec2RuntimeMonitor) EC2 runtime monitor is a serverless solution to get a notification when an EC2 instance is running for a time exceeding a user defined threshold. The README covers use cases why you might find this useful, but principally cost optimisation as well as reducing your carbon footprint are two key reasons why this might be a useful tool to keep your toolkit.

**rds-extended-support-cost-estimator**

[rds-extended-support-cost-estimator](https://github.com/aws-samples/rds-extended-support-cost-estimator) provides scripts can be used to help estimate the cost of RDS Extended Support for RDS instances & clusters in your AWS account and organisation. In September 2023, we announced Amazon RDS Extended Support, which allows you to continue running your database on a major engine version past its RDS end of standard support date on Amazon Aurora or Amazon RDS at an additional cost. These scripts should be run from the payer account of your organisation to identify the RDS clusters in your organisation that will be impacted by the extended support and the estimated additional cost. Check the README for additional details as to which database engines it will scan and provide estimations for.

**shuk**

[shuk](https://github.com/darko-mesaros/shuk) my colleague Darko Mesaros has been experimenting with Rust, and he has created shuk, a file sharing tool (in Rust) for Amazon S3. Run the tool with any file you want to upload, and it will generated a pre-signed URL ready for you to use. Very much alpha, so keep watching (and if you feel so inclined, contribute).

**rockhead-extensions**

[rockhead-extensions ](https://github.com/fbouteruche/rockhead-extensions)another repo from a colleague, this time it is .NET aficionado Francois Bouteruche, who has put together this repo that provides code (as well as a nuget package) to make your .NET developer life easier when you invoke foundation models on Amazon Bedrock. More specifically, Francois has created a set of extension methods for the AWS SDK for .NET Bedrock Runtime client. It provides you strongly typed parameters and responses to make your developer life easier.

**mlspace**

[mlspace](https://github.com/awslabs/mlspace) provides code that will help you deploy [MLSpace](https://mlspace.readthedocs.io/en/latest/) into your AWS account. [MLSpace](https://mlspace.readthedocs.io/en/latest/) is an open source no-hassle tool for data science, machine learning and deep learning, and has pre-made environments for pytorch, tensorflow and everything else you might need.

### Demos, Samples, Solutions and Workshops

**smart-assistant-agent**

[smart-assistant-agent](https://github.com/dashapetr/smart-assistant-agent) is a project from AWS Community Builder Darya Petrashka that provides a solution to building an AWS Bedrock agent acting as a Telegram chat assistant. Check out the README for example videos of what this can do, as well as very detailed deployment instructions.

![architecture for smart assistant](https://github.com/dashapetr/smart-assistant-agent/blob/main/images/agent_architecture.jpg?raw=true)

**apigw-multi-region-failover**

[apigw-multi-region-failover](https://github.com/aws-samples/apigw-multi-region-failover) provides demo code that demonstrates an Amazon API Gateway multi-region active-passive public API that proxies two independent multi-region active-passive service APIs. The primary and secondary regions can be configured independently for the external API and each service. This allows you to fail over the external API and each service independently as needed for disaster recovery.

![architecture of multi region apigw](https://github.com/aws-samples/apigw-multi-region-failover/blob/main/images/diagram.jpg?raw=true)

**aws-piday2024**

[aws-piday2024 ](https://github.com/debnsuma/aws-piday2024)my colleague Suman Debnath has put together this AWS Pi Day 2024 repository, where you can explore various applications and examples using Amazon Bedrock, fine-tuning, and Retrieval-Augmented Generation (RAG).

![demo of RAG application](https://github.com/debnsuma/aws-piday2024/raw/main/images/Resume-Screener.gif)

**amplify-hosting-astro**

[amplify-hosting-astro](https://github.com/mauerbac/amplify-hosting-astro) is a repo from AWS Amplify's Matt Auerbach that provides a walk through on how to build a simple blog using Astro's starter blog template, and deploy it using AWS Amplify Hosting.

![example home page for astro on amplify](https://github.com/mauerbac/amplify-hosting-astro/blob/main/landing_page.png?raw=true)

### AWS and Community blog posts
 
Each week I spent a lot of time reading posts from across the AWS community on open source topics. In this section I share what personally caught my eye and interest, and  I hope that many of you will also find them interesting. 

**The best from around the Community**

Another stellar round up from the AWS Community this week, and given it is KubeCon I am going to start off with AWS Community Builder Gargee Bhatnagar who has put together [Deploy of Application in Nodes for Amazon Elastic Kubernetes Service](https://dev.to/aws-builders/deploy-of-application-in-nodes-for-amazon-elastic-kubernetes-service-5acm), who provides one of the nicer walk throughs of how to install an application (in this case NGNIX) on Amazon EKS. Sticking with Amazon EKS, although shifting slightly location wise, we have Amit Gupta from Isovalant who has put together [Cilium in EKS-Anywhere](https://isovalent.com/blog/post/cilium-eks-anywhere/), an overview of what EKS-Anywhere is, and how to install Cilium in  EKS-Anywhere. Cannot wait for the follow up post, well worth a read folks. The last Kubernetes post this week is from AWS Community Builder Oluwafemi Lawal, who has penned [Navigating AWS EKS with Terraform: Understanding EKS Cluster Configuration](https://dev.to/aws-builders/navigating-aws-eks-with-terraform-understanding-eks-cluster-configuration-2f6o). If you are looking for details on how to provision your Amazon EKS clusters with Terraform, they why not start here.

From Kubernetes we switch to Rust, with AWS Community Builder Benjamen Pyle sharing his knowledge of Rust as he shows you how to build a CRUD based API in Rust, that is deployed on AWS Lambda with AWS CDK. If that sounds like your cup of tea, then read on in [A Proven and Comprehensive Pattern for Building an API with Rust and Lambda](https://dev.to/aws-builders/a-proven-and-comprehensive-pattern-for-building-an-api-with-rust-and-lambda-2aol). AWS Community Builder Jatin Mehrotra shares how you can implement security and compliance by shifting left, implementing DevSecOps practices during the infrastructure development phase to achieve security by design. Read [Level-Up Your AWS CDK Game: Shift Left Security Unveiled!](https://dev.to/aws-builders/level-up-your-aws-cdk-game-shift-left-security-unveiled-5f54) and find out how this can reduce risks and issues of cloud infrastructure misconfigurations, and how you can use policy validation tools such as Keeping Infrastructure as Code Secure(KICS) to help.

Marcin Sodkiewicz writes [AWS & OpenTelemetry: SQS context propagation](https://sodkiewiczm.medium.com/aws-opentelemetry-sqs-instrumentation-50f2d0949825), and shares how to instrument your AWS async processing based on SQS with OpenTelemetry. Very nice post, and love the visuals on this one. AWS Community Builder Vadym Kazulkin continues his quest to help Java developers optimise their cold start performance in the latest instalment of his series, [AWS SnapStart - Part 17 Impact of the snapshot tiered cache on the cold starts with Java 21](https://dev.to/aws-builders/aws-snapstart-part-17-impact-of-the-snapshot-tiered-cache-on-the-cold-starts-with-java-21-52ef).  In this episode, he dives deep into "tiered caching". To finish up this week we have a couple of OpenSearch related posts. AWS Community Builder Alexey Vidanov has put together [Find It Fast: Streamline Phone Number Searches with OpenSearch](https://dev.to/aws-builders/find-it-fast-streamline-phone-number-searches-with-opensearch-1aol) that shows you how OpenSearch empowers you to achieve blazing-fast and accurate phone number searches using edge ngrams and custom analysers. To close this week is Szymon Szym with [OpenSearch with AWS Lambda Rust (part 2) - business logic ](https://dev.to/aws-builders/opensearch-with-aws-lambda-rust-part-2-business-logic-2fnf), the follow up post on his series of how you can do local test and development of OpenSearch with AWS Lambda. 

**InfluxDB**

If you missed the announcement last week, InfluxDB, an open source time series database written in Rust, using Apache Arrow, Apache Parquet, and Apache DataFusion as its foundational building blocks, is now available via Amazon Timestream for InfluxDB. Timestream for InfluxDB makes it easy for application developers and DevOps teams to run fully managed InfluxDB databases on AWS for real-time time-series applications using open-source APIs. 

My colleague Donnie Prakoso put together a post, [Run and manage open source InfluxDB databases with Amazon Timestream](https://aws.amazon.com/blogs/aws/run-and-manage-open-source-influxdb-databases-with-amazon-timestream/) that provides a great way to learn more about this launch and how to get started, and my Derek Bingham has also put together a very handy video. Check it out.

{{< youtube yxlejP95ezM >}}


Timestream for InfluxDB offers the full feature set available in the InfluxDB 2.7 release of the open-source version, and adds deployment options with Multi-AZ high availability and enhanced durability.

**Other posts and quick reads**

* [Procure and deploy third-party EKS add-ons without leaving the EKS console](https://aws.amazon.com/blogs/awsmarketplace/procure-deploy-third-party-eks-add-ons-eks-console/)  shows you how to discover, subscribe to, and deploy a FIPS complaint Solo.io Istio service mesh using Amazon EKS add-on framework [hands on]
* [How VMware Tanzu CloudHealth migrated from self-managed Kafka to Amazon MSK](https://aws.amazon.com/blogs/big-data/how-vmware-tanzu-cloudhealth-migrated-from-self-managed-kafka-to-amazon-msk/) explores how VMware Tanzu CloudHealth migrated from self managed Apache Kafka to Amazon MSK, exploring their journey and sharing insights learned
* [Best practices to implement near-real-time analytics using Amazon Redshift Streaming Ingestion with Amazon MSK](https://aws.amazon.com/blogs/big-data/best-practices-to-implement-near-real-time-analytics-using-amazon-redshift-streaming-ingestion-with-amazon-msk/)  looks at the best practices to implement near-real-time analytics using Amazon Redshift streaming ingestion with Amazon MSK [hands on]
* [Real-time cost savings for Amazon Managed Service for Apache Flink](https://aws.amazon.com/blogs/big-data/real-time-cost-savings-for-amazon-managed-service-for-apache-flink/) covers some aspects to consider when attempting cost-savings measures for Managed Service for Apache Flink
* [VTEX scales to 150 million metrics using Amazon Managed Service for Prometheus](https://aws.amazon.com/blogs/mt/scaling-to-150-million-metrics-using-amazon-managed-service-for-prometheus/) is a case study on how VTEX managed observability using Amazon Managed Service for Prometheus to maximise operational engineering efficiency

![overview of VTEX sharding architecture](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2024/03/01/arch_customer_amp.jpg)

* [In-stream anomaly detection with Amazon OpenSearch Ingestion and Amazon OpenSearch Serverless](https://aws.amazon.com/blogs/big-data/in-stream-anomaly-detection-with-amazon-opensearch-ingestion-and-amazon-opensearch-serverless/) looks at a solution using OpenSearch Ingestion that empowers you to perform in-stream anomaly detection within your own AWS environment [hands on]
* [Deploying Trino on EKS](https://awslabs.github.io/data-on-eks/docs/blueprints/distributed-databases/trino) provides details a blueprint that will deploy Trino on an Amazon EKS cluster (Kubernetes version 1.29) with nodes provisioned using Karpenter [hands on]

### Quick updates

**Apache Kafka**

Amazon MSK Replicator now supports replicating existing data on your topics across Amazon Managed Streaming for Apache Kafka (Amazon MSK) clusters. With this new configuration, you can now start replication from earliest position in your source cluster's topics in addition to latest position. Amazon MSK Replicator is a feature of Amazon MSK that enables you to reliably replicate data across Amazon MSK clusters in different or the same AWS region(s) in a few clicks. With MSK Replicator, you can easily build regionally resilient streaming applications for increased availability and business continuity.

**AWS ParallelCluster**

AWS ParallelCluster is a fully-supported and maintained open-source cluster management tool that enables R&D customers and their IT administrators to operate high-performance computing (HPC) clusters on AWS. AWS ParallelCluster is designed to automatically and securely provision cloud resources into elastically-scaling HPC clusters capable of running scientific, engineering, and machine-learning (ML/AI) workloads at scale on AWS.  AWS ParallelCluster 3.9 is now generally available. Key features of this release include support for Red Hat Enterprise Linux 9 (RHEL9), Rocky Linux 9 and the ability to resize a cluster's compute capacity without stopping it. Other important features in this release include:

* support for mounting user-defined file systems in AWS without stopping the cluster.
* Ability to disable sudo privileges for the default cluster user.

For more details on the release, review the [AWS ParallelCluster 3.9 release notes](https://github.com/aws/aws-parallelcluster-cookbook/releases/tag/v3.9.0).

**MySQL**

A couple of updates this week for users of MySQL on Amazon Aurora.

First up is news is that  MySQL 3.06 (compatible with MySQL 8.0.34) is generally available. In addition to security enhancements, bug fixes, and improved data replication performance with binary log (binlog), this release includes new generative AI capabilities and improved cross-region resiliency for Aurora Global Database. With this release, customers can use Aurora MySQL to build scalable generative AI applications, accessing Amazon Bedrock’s foundation models directly through SQL. This release also contains improvements that bolster the cross-region resiliency of Aurora Global Database, enabling secondary regions to seamlessly serve read requests if the primary writer were to become unavailable during an instance restart. For more details, refer to the Aurora MySQL 3 and MySQL 8.0.34 release notes. To upgrade, you can initiate a minor version upgrade manually by modifying your DB cluster, or you can enable the “Auto minor version upgrade” to allow automatic upgrades in the upcoming maintenance window.

Following that is news that Amazon Aurora ML now provides access to foundation models available in Amazon Bedrock directly through SQL in the Aurora MySQL 3.06 version. Amazon Aurora ML exposes models as SQL functions, allowing you to use standard SQL to pass data to models and return model output as query results. It provides simple, optimised, and secure integration between Aurora and AWS machine learning services without having to build custom integrations or move data around. As an example, Aurora ML and Bedrock together can enable real-time summarisation of customer support notes in Aurora to accelerate case resolution. Aurora ML can also pass current and relevant database information to Bedrock to improve chatbot responses.

**Cedar**

This [tweet](https://twitter.com/micahhausler/status/1767967030819377386) caught my eye last week. Michael has been playing with Cedar and Kubernetes, and he is cooking up something interesting. One to watch.

### Videos of the week

**Talking with management about open source**

Fresh from FOSSBackstage a few weeks back, Rich Bowen from AWS provides a really great talk about how to engage with senior stakeholders within your business about open source. Essential viewing.

{{< youtube 6W5vI8y7Bis >}}


**Rust efficiencies at AWS scale**

Tim McNamara is known as New Zealand’s Rust guy. He is the author of Rust in Action, and also a Senior Software Engineer at AWS, where he helps other builders with all things Rust. Check out this edition of Changelog Ship It to hear more about how AWS is leveraging Rust (and also, consider subscribing to the Changelog channel to keep with all the awesome content they produce).

{{< youtube JdGvurkw7Ws >}}


### Events for your diary

If you are planning any events in 2024, either virtual, in person, or hybrid, get in touch as I would love to share details of your event with readers. 

I recently found this GitHub repo, [open-source-events](https://github.com/Everything-Open-Source/open-source-events) that is a curated set of open source events for 2024. Go check it out and see what 2024 is looking like.

**KubeCon / CloudNativeCon**
**Paris, 19th-22nd March**

Join AWS speakers at KubeCon Europe this week as they dive into the latest open source innovations innovations that make AWS the best place for customers to build and run open source software in the cloud. AWS conference speakers will be talking about Karpenter, Argo CD apps, the integration of AI in the CloudNative world, multi-tenant scalable Prometheus with Cortex, eBPF, Cloud Native CAKES stack for Zero Trust, chaos engineering, Kubernetes controllers, OpenTelemetry, and zonal outages. Don’t miss this opportunity to enhance your knowledge and connect with AWS experts.

Find out more by checking out the post from Chris Potter, [AWS at KubeCon + CloudNativeCon Europe 2024](https://community.aws/content/2d2VUe0kSVb9x2fkuTn4zhnwaHN)

**FOSSASIA**
**April 8th-10th, Hanoi, Vietnam**

The FOSSASIA Summit is one of Asia's Premier Open Technology conference with thousands of participants and an Open Tech exhibition taking place every year in March, and this year it will be in the vibrant city of Hanoi, Vietnam. A number of my AWS colleagues will be there as well as myself, so I look forward to meeting with some of you. You can find out more details about this event by checking out the [FOSSASIA event page](https://fossasia.org/)

**Everything Open**
**April 16th-18th, Gladstone Australia**

Everything Open is an open source event where the open source community come together for three days to share updates on their projects and learn about the latest in open technologies from leading community members. The conference will cover a broad range of topics across three days. You can expect to see talks from areas such as the Linux ecosystem, including the Kernel, distros and drivers. There will also be a number of presentations on open source software and open hardware, alongside talks on Galleries, Libraries, Archives and Museums (GLAM), open data, open government, and much more. Another key feature will be talks on building and managing communities around open technologies. I will be attending and doing some open source talks, as well as finding out more about the local open source community.

Check out [the event website](https://2024.everythingopen.au/)for more details, and hope to see some of you there.

**OpenSearchCon Europe**
**May 6th-7th, Berlin Germany**

I am happy to share news of the launch of a European edition of OpenSearchCon, so make sure you mark these dates in your diary. OpenSearchCon Europe has now joined OpenSearchCon North America on our 2024 conference schedule. Read more about the event in the post, [Announcing OpenSearchCon Europe 2024](https://opensearch.org/blog/announcing-opensearchcon-europe-2024/)

**Cortex**
**Every other Thursday, next one 16th February**

The Cortex community call happens every two weeks on Thursday, alternating at 1200 UTC and 1700 UTC. You can check out the GitHub project for more details, go to the [Community Meetings](https://github.com/cortexproject/cortex#community-meetings) section. The community calls keep a rolling doc of previous meetings, so you can catch up on the previous discussions. Check the [Cortex Community Meetings Notes](https://docs.google.com/document/d/1shtXSAqp3t7fiC-9uZcKkq3mgwsItAJlH6YW6x1joZo/edit) for more info.

**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://www.meetup.com/OpenSearch/)

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes:  Darya Petrashka, Marcin Sodkiewicz,  Francois Bouteruche, Darko Mesaros,  Suman Debnath, Swaminathan Jayaraman, Wendy Jabitta, Donnie Prakoso, Derek Bingham, Rich Bowen, Tim McNamara, Rivlin Pereira, Raj Ramasubbu, Satya Pattanaik, Todd McGrath, Vaibhav Pandey, Rivlin Pereira, Vaibhav Pandey,  Jeremy Ber, Lorenzo Nicora, Poulomi Dasgupta, Adekunle Adedotun, Jose Augusto Ferronato, Rupesh Tiwari, Muthu Pitchaimani,  Gargee Bhatnagar, Amit Gupta, Oluwafemi Lawal, Benjamen Pyle, Jatin Mehrotra,  Vadym Kazulkin, Alexey Vidanov, Szymon Szym, and Matt Auerbach.

**Feedback**

Please please please take 1 minute to [complete this short survey](https://www.pulse.aws/promotion/10NT4XZQ). 

### Stay in touch with open source at AWS

Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) for more open source goodness.

One of the pieces of feedback I received in 2023 was to create a repo where all the projects featured in this newsletter are listed. Where I can hear you all ask? Well as you ask so nicely, you can meander over to[ newsletter-oss-projects](https://github.com/094459/newsletter-oss-projects).

Made with ♥ from DevRel