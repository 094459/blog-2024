---
title: 'AWS open source newsletter #199'
date: '2024-06-10'
tags : [ oss-newsletter, aws open source, Valkey, .NET Core, Babelfish for PostgreSQL, PostgreSQL, MySQL, Kubernetes, Amazon EKS, Apache Kafka, Apache Livy, Jupyter, Amazon EMR, AWS ParallelCluster, Apache TinkerPop, GraphQL, Apache Flink, sustainability-scanner, YugabyteDB, LangChain, DSPy, Argo Workflows, CNOE, projen]
canonicalUrl: "https://community.aws/content/2hgOKawTtLBR1DJjBa8KlLPTVio/aws-open-source-newsletter-199"
---

##  Edition #199

Welcome to issue #199 of the AWS open source newsletter, the newsletter where we try and provide you the best open source on AWS content.  I cannot believe that we are one issue away from a pretty significant milestone. I would love to hear from some of the regular readers of this newsletter to find any highlights they have had, or perhaps things they have found that have been pretty significant. Hit me up so I can share some of those stories.

New projects this week include an updated Python library when working with Amazon RDS databases, the very cool new way to deploy frontends to AWS, an alternative to NAT Gateways, a couple of cool tools for CloudFormation users, a new serverless framework that works with GPUs, and some demo repos that feature generative AI and one of my favourite AWS security features, Nitro Enclaves. Also featured in this edition is content on Valkey, .NET, Babelfish for PostgreSQL, PostgreSQL, MySQL, Kubernetes, Apache Kafka, Apache Livy, Jupyter, Amazon EMR, AWS ParallelCluster, Apache TinkerPop, GraphQL, Apache Flink, sustainability-scanner, YugabyteDB, LangChain, DSPy, Argo Workflows, and CNOE. Check out the videos and events section at the end, and as always, if you have an open source event you want me to include, just drop me the details. 

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution. The projects mentioned here do not represent any formal recommendation or endorsement, I am just sharing for greater awareness as I think they look useful and interesting!*

### Tools

**aws-advanced-python-wrapper**

[aws-advanced-python-wrapper](https://github.com/aws/aws-advanced-python-wrapper) is complementary to and extends the functionality of an existing Python database driver to help an application take advantage of the features of clustered databases on AWS. It wraps the open-source Psycopg and the MySQL Connector/Python drivers and supports Python versions 3.8 or newer. You can install the aws-advanced-python-wrapper package using the pip command along with either the psycpg or mysql-connector-python open-source packages. The wrapper driver relies on monitoring database cluster status and being aware of the cluster topology to determine the new writer. This approach reduces switchover and failover times from tens of seconds to single digit seconds compared to the open-source drivers. Check the README for more details and example code on how to use this.

**cloudfront-hosting-toolkit**

[cloudfront-hosting-toolkit](https://github.com/awslabs/cloudfront-hosting-toolkit) is a new an open source command line tool to help developers deploy fast and secure frontends in the cloud. This project offers the convenience of a managed frontend hosting service while retaining full control over the hosting and deployment infrastructure to make it your own. The CLI simplifies AWS platform interaction for deploying static websites. It walks you through configuring a new repository, executing the deployment process, and provides the domain name upon completion. By following these steps, you effortlessly link your GitHub repository and deploy the necessary infrastructure, simplifying the deployment process. This enables you to focus on developing website content without dealing with the intricacies of infrastructure management. A few of my colleagues have tried this out and they are loving it. You can also find out more by reading the blog post, [Introducing CloudFront Hosting Toolkit](https://aws.amazon.com/blogs/networking-and-content-delivery/introducing-cloudfront-hosting-toolkit/) where Achraf Souk, Corneliu Croitoru, and Cristian Graziano help you get started with a hands on guide to this project.

![cloudfront hosting toolkit event flow](https://d2908q01vomqb2.cloudfront.net/5b384ce32d8cdef02bc3a139d4cac0a22bb029e8/2024/03/11/diag-hosting-1.png)

**terraform-aws-alternat**

[terraform-aws-alternat](https://github.com/chime/terraform-aws-alternat) simplifies how you can deploy high availability implementation of AWS NAT instances, which may help you to reduce your AWS costs if you need to provide internet access within your VPC's. It is worth checking out the README which provides details and comparisons on using this approach vs NAT Gateways.

![overview of nat instance solution](https://github.com/chime/terraform-aws-alternat/blob/main/assets/architecture.png?raw=true)

**cfn-changeset-viewer**

[cfn-changeset-viewer](https://github.com/trek10inc/cfn-changeset-viewer) is a tool all developers who work with and use AWS CloudFormation will want to check out. cfn-changeset-viewer is a CLI that will view the changes calculated in a CloudFormation ChangeSet in a more human-friendly way, including rendering details from a nested change set. Diffs are displayed in a logical way, making it easy to see changes, additions and deletions. Checkout the doc for more details and an example.

**outtasync**

[outtasync](https://github.com/dhth/outtasync) helps users quickly identify the CloudFormation stacks that have gone out of sync with the state represented by their counterpart stack files. This can occur when someone updates a stack but fails to commit the latest stack file to the codebase. Alternatively, it may happen when a stack is updated on one deployment environment but not on others. Great documentation with examples and a video that provides everything you need to know.

**beta9**

[beta9](https://github.com/beam-cloud/beta9) is a self-hosted serverless framework that you can run in your AWS account. Think of AWS Lambda, but with GPUs and a Python-first developer experience. You can run workloads that instantly scale up to thousands of GPU containers running in parallel. The instances scale down automatically after each workload. You can also do things like deploy web endpoints, run task queues, and mount storage volumes for accessing large datasets. If you already have an EKS cluster, you can install Beta9 with a Helm chart. We think this would be a great way to save money on EC2 GPU resources while also getting a magical Python-first developer experience. If you have feedback or feature ideas, the maintainers would like to hear them. 

**qgis-amazonlocationservice-plugin**

[qgis-amazonlocationservice-plugin](https://github.com/dayjournal/qgis-amazonlocationservice-plugin) is a new open source plugin from AWS Hero Yasunori Kirimoto that uses the functionality of Amazon Location Service for  the Geographic Information System (GIS), a user friendly Open Source application licensed under the GNU General Public License. You can find out more by reading his post, [Amazon Location Service Plugin for QGIS released in OSS](https://community.aws/content/2h3Ego2EPiPqLQusOeuMocNNQUV/amazon-location-service-plugin-for-qgis-released-in-oss)


### Demos, Samples, Solutions and Workshops

**amazon-bedrock-serverless-prompt-chaining**

[amazon-bedrock-serverless-prompt-chaining](https://github.com/aws-samples/amazon-bedrock-serverless-prompt-chaining/) This repository provides examples of using AWS Step Functions and Amazon Bedrock to build complex, serverless, and highly scalable generative AI applications with prompt chaining. Prompt chaining is a technique for building complex generative AI applications and accomplishing complex tasks with large language models (LLMs). With prompt chaining, you construct a set of smaller subtasks as individual prompts. Together, these subtasks make up your overall complex task that you would like the LLM to complete for your application. To accomplish the overall task, your application feeds each subtask prompt to the LLM in a pre-defined order or according to a set of defined rules. There are lots of examples in the README, so check this out to find out more about prompt chaining, and how you can do it serverless stylii!


**how-high-is-my-salary-enclave-app**

[how-high-is-my-salary-enclave-app](https://github.com/richardfan1126/how-high-is-my-salary-enclave-app) is a rather cool project from AWS Hero Richard Fan that provides a simple app showcases how to protect software supply chain security using GitHub Actions, SLSA, and AWS Nitro Enclaves.


### AWS and Community blog posts
 
Each week I spent a lot of time reading posts from across the AWS community on open source topics. In this section I share what personally caught my eye and interest, and  I hope that many of you will also find them interesting. 

**The best from around the Community**

Starting things off this week is AWS Hero Franck Pachot who shares how to provision YugabyteDB, an open-source PostgreSQL-compatible distributed SQL database, on Amazon EKS in a multi-region setup in [Distributed PostgreSQL with YugabyteDB Multi-Region Kubernetes / Istio / Amazon EKS](https://dev.to/aws-heroes/distributed-postgresql-with-yugabytedb-multi-region-kubernetes-istio-amazon-eks-366a).

Any post that quotes Douglas Adams is always going to get my attention, so I enjoyed reading João Galego's latest post, [Running LangChain.js Applications on AWS Lambda](https://community.aws/content/2grhh3vrinYLsg3xkFNCe4LCcUL/running-langchain-js-applications-on-aws-lambda) where he shows you how to run LangChain.js apps that are powered by Amazon Bedrock on AWS Lambda, using function URLs and response streaming. No towels required (you will have to be an Adam's fan to understand that one I'm afraid. Staying with generative AI, we move onto DSPy, an open source framework for algorithmically optimising LM prompts and weights. Randy D has put together [Automatic LLM prompt optimization with DSPY](https://community.aws/content/2hCPveNeYXY7fSdaDQLtfv2uo9Q/automatic-llm-prompt-optimization-with-dspy), and walks you through how to get started with is framework.

Cloud Native Operational Excellence (aka, CNOE, pronounced Kuh.no) is a joint effort among a number of organisations to share developer tooling, thoughts, and patterns to help organizations make informed technology choices and resolve common pain points. [Argo Workflows Controller Scalability Testing on Amazon EKS](https://cnoe.io/blog/argo-workflow-scalability) is the latest blog post from Andrew Lee and Vikram Sethi, they publish details on scalability experiments on running Argo Workflows executing Workflows via two different load patterns. Great read if you want to see how the impact as deployments scale - plenty of great data points and graphs.

Closing things this week is a post that is perfect if you are struggling with IAM permissions with your Amazon EKS workloads.  AWS Community Builder Saifeddine Rajhi's latest post might be just the thing to help. Dive into [Easy AWS permissions for your EKS workloads: Pod Identity - An easy way to grant AWS access](https://dev.to/aws-builders/easy-aws-permissions-for-your-eks-workloads-pod-identity-an-easy-way-to-grant-aws-access-13oj) explores what EKS Pod Identity is, how it works, and why you should consider using it for your Kubernetes applications running on EKS.
 
 **sustainability-scanner**
 
 Featured in a previous issue of this newsletter ([#156](https://dev.to/aws/aws-open-source-newsletter-156-lim) [sustainability-scanner](https://github.com/awslabs/sustainability-scanner) is an open source tool designed to help customers create a more sustainable infrastructure on AWS by evaluating your infrastructure as code against a set of sustainability best practices and suggested improvements to apply to your code. Maurits de Groot and Jyri Seiger provide more info including how to get works, how to started in their, and how to incorporate this as part of your continuous  integration/deployment processes in the post, [Build More Sustainable AWS Workloads with the Sustainability Scanner](https://aws.amazon.com/blogs/opensource/build-more-sustainable-aws-workloads-with-the-sustainability-scanner/).
 
**Other posts to check out**

* [Introducing Amazon EMR on EKS with Apache Flink: A scalable, reliable, and efficient data processing platform](https://aws.amazon.com/blogs/big-data/introducing-amazon-emr-on-eks-with-apache-flink-a-scalable-reliable-and-efficient-data-processing-platform/)  introduces the features of EMR on EKS with Apache Flink, discuss their benefits, and highlight how to get started
* [Create a fallback migration plan for your self-managed MySQL database to Amazon Aurora MySQL using native bi-directional binary log replication](https://aws.amazon.com/blogs/database/create-a-fallback-migration-plan-for-your-self-managed-mysql-database-to-amazon-aurora-mysql-using-native-bi-directional-binary-log-replication/) looks at how you can set up bi-directional replication between an on-premises MySQL instance and an Aurora MySQL instance [hands on]
* [Automate interval partitioning maintenance and monitoring in Amazon RDS for PostgreSQL and Amazon Aurora PostgreSQL – Part 2](https://aws.amazon.com/blogs/database/automate-interval-partitioning-maintenance-and-monitoring-in-amazon-rds-for-postgresql-and-amazon-aurora-postgresql-part-2/) demonstrates how you can monitor and send alerts using PostgreSQL extensions like pg_cron, aws_lambda [hands on]

![overview of the architecture for partition monitoring and alerting](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2024/05/23/dbblog_2396_architecture.jpg)

* [Benchmark Amazon RDS for PostgreSQL Single-AZ DB instance, Multi-AZ DB instance, and Multi-AZ DB Cluster deployments](https://aws.amazon.com/blogs/database/benchmark-amazon-rds-for-postgresql-single-az-db-instance-multi-az-db-instance-and-multi-az-db-cluster-deployments/) presents a qualitative performance comparison between RDS for PostgreSQL Single-AZ DB instance, Multi-AZ DB instance, and Amazon RDS Multi-AZ DB Cluster deployments
* [Best practices for AWS AppSync GraphQL APIs](https://aws.amazon.com/blogs/mobile/best-practices-for-aws-appsync-graphql-apis/) provides a guide to help you look at strategies that you should consider when building out your GraphQL API
* [How Freddie Mac used Amazon EKS to modernize their platform and migrate applications](https://aws.amazon.com/blogs/containers/how-freddie-mac-used-amazon-eks-to-modernize-their-platform-and-migrate-applications/) is a case study on how Freddie Mac built a platform on Amazon EKS that allowed them to migrate and modernise their apps at a faster pace

![overview of their gitops architecture](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2024/05/17/Picture9-2.png)

* [Securing HPC on AWS: implementing STIGs in AWS ParallelCluster](https://aws.amazon.com/blogs/hpc/securing-hpc-on-aws-implementing-stigs-in-aws-parallelcluster/) walks you through the process of applying Security Technical Implementation Guides (STIGs, a set of standards maintained by the US government) to your ParallelCluster environment [hands on]
* [Unit testing Apache TinkerPop transactions: From TinkerGraph to Amazon Neptune](https://aws.amazon.com/blogs/database/unit-testing-apache-tinkerpop-transactions-from-tinkergraph-to-amazon-neptune/) shows how you can use TinkerGraph to unit test your transactional workloads, as well as how to use TinkerGraph in embedded mode [hands on]
* [Deploying Multiple Large Language Models with NVIDIA Triton Server and vLLM](https://awslabs.github.io/data-on-eks/docs/gen-ai/inference/vLLM-NVIDIATritonServer-Llama2) shows you how to deploy multiple Large Language Models with NVIDIA Triton Server and vLLM on Amazon EKS via the Data on EKS project [hands on]

![overview of architecture](https://awslabs.github.io/data-on-eks/assets/images/triton-architecture-26f45e98081552c17f8381dbb7dd5f61.png)

### Quick updates

**Kubernetes**

Kubernetes version 1.30 introduced several new features and bug fixes, and AWS is excited to announce that you can now use Amazon EKS and Amazon EKS Distro to run Kubernetes version 1.30. Starting today, you can create new EKS clusters using v1.30 and upgrade your existing clusters to v1.30 using the Amazon EKS console, the eksctl command line interface, or through an infrastructure-as-code tool. Kubernetes version 1.30 includes stable support for pod scheduling readiness and minimum domains parameter for PodTopologySpread constraints. As a reminder, starting with Kubernetes version 1.30 or newer, any newly created managed node groups will automatically default to using AL2023 as the node operating system.

**Apache Kafka**

Amazon Managed Streaming for Apache Kafka (Amazon MSK) is a fully managed service for Apache Kafka and Kafka Connect that makes it easier for you to build and run applications that use Apache Kafka as a data store. Amazon MSK now supports Apache Kafka version 3.7 for new and existing clusters. Apache Kafka version 3.7 includes several bug fixes and new features that improve performance. Key improvements include latency improvements resulting from leader discovery optimizations during leadership changes, as well as log segment flush optimisation options. For more details and a complete list of improvements and bug fixes, see the Apache Kafka release notes for version 3.7.

In more news, Amazon MSK also now supports KRaft mode (Apache Kafka Raft) in Apache Kafka version 3.7. The Apache Kafka community developed KRaft to replace Apache ZooKeeper for metadata management in Apache Kafka clusters. In KRaft mode, cluster metadata is propagated within a group of Kafka controllers, which are part of the Kafka cluster, versus across ZooKeeper nodes. On Amazon MSK, like with ZooKeeper nodes, KRaft controllers are included at no additional cost to you, and require no additional setup or management. You can now create clusters in either KRaft mode or ZooKeeper mode on Apache Kafka version 3.7. In Kraft mode, you can add up to 60 brokers to host more partitions per-cluster, without requesting a limit increase, compared to the 30-broker quota on Zookeeper-based clusters. Support for Apache Kafka version 3.7 is offered in all AWS regions where Amazon MSK is available. 

If you are interested in learning more about this, I suggest reading [Introducing support for Apache Kafka on Raft mode (KRaft) with Amazon MSK clusters](https://aws.amazon.com/blogs/big-data/introducing-support-for-apache-kafka-on-raft-mode-kraft-with-amazon-msk-clusters/) where Kalyan Janak shares his excitement and walks you through some details around how KRaft mode helps over the ZooKeeper approach,   the process of creating MSK clusters with KRaft mode, and thenhow to connect your application to MSK clusters with KRaft mode.

**Apache Livy**

Amazon EMR Serverless now supports endpoints for Apache Livy. Customers can now securely connect their Jupyter notebooks and manage Apache Spark workloads using Livy’s REST interface. With the Livy endpoints, setting up a connection is easy - just point your Livy client in your on-premises notebook running Sparkmagic kernels to the EMR Serverless endpoint URL. You can now interactively query, explore and visualise data, and run Spark workloads using Jupyter notebooks without having to manage clusters or servers. In addition, you can use the Livy REST APIs for use cases that need interactive code execution outside notebooks. This feature is generally available on EMR release versions 6.14 and later.

**MySQL**

Amazon Aurora MySQL 3.07 (with MySQL 8.0 compatibility) now supports MySQL 8.0.36. In addition to security enhancements and bug fixes in MySQL 8.0.36, Amazon Aurora MySQL 3.07 includes several fixes and general improvements. For more details, refer to the Aurora MySQL 3 and MySQL 8.0.36.

**PostgreSQL**

Amazon RDS for PostgreSQL 17 Beta 1 is now available in the Amazon RDS Database Preview Environment, allowing you to evaluate the pre-release of PostgreSQL 17 on Amazon RDS for PostgreSQL. You can deploy PostgreSQL 17 Beta 1 in the Amazon RDS Database Preview Environment that has the benefits of a fully managed database.

PostgreSQL 17 includes updates to vacuuming that reduces memory usage, improves time to finish vacuuming, and shows progress of vacuuming indexes. With PostgreSQL 17, you no longer need to drop logical replication slots when performing a major version upgrade. PostgreSQL 17 continues to build on the SQL/JSON standard, adding support for `JSON_TABLE` features that can convert JSON to a standard PostgreSQL table. The `MERGE` command now supports the `RETURNING` clause, letting you further work with modified rows. PostgreSQL 17 also includes general improvements to query performance and adds more flexibility to partition management with the ability to SPLIT/MERGE partitions. 

**Take Note!** Amazon RDS Database Preview Environment database instances are retained for a maximum period of 60 days and are automatically deleted after the retention period.

**Babelfish for PostgreSQL**

AWS Database Migration Service (AWS DMS) now supports Babelfish for Aurora PostgreSQL as a source by enhancing its existing PostgreSQL endpoint to handle Babelfish data types. Babelfish is a feature of Amazon Aurora PostgreSQL-Compatible Edition that enables Aurora to understand commands from applications written for Microsoft SQL Server. AWS DMS supports both Full Load and Change Data Capture (CDC) migration modes for Babelfish. Full Load migration copies all of the data from the source database and CDC copies only the data that has changed since the last migration.

**.NET on AWS **

AWS Elastic Beanstalk is a service that provides the ability to deploy and manage applications in AWS without worrying about the infrastructure that runs those applications. AWS Elastic Beanstalk now supports .NET 8 on AL2023 Elastic Beanstalk environments. Elastic Beanstalk .NET 8 on AL2023 environments come with .NET 8.0 installed by default. See Release Notes for additional details.  .NET 8 on AL2023 runtime adds security improvements, such as support for the SHA-3 hashing algorithm, along with other updates including enhanced dynamic profile-guided optimisation (PGO) that can lead to runtime performance improvements, and better garbage collection with the ability to adjust the memory limit on the fly. You can create Elastic Beanstalk environment(s) running .NET 8 on AL2023 using any of the Elastic Beanstalk interfaces such as Elastic Beanstalk Console, Elastic Beanstalk CLI, Elastic Beanstalk API, and AWS Toolkit for Visual Studio.

### Videos of the week

**Building projen-pipelines in public - Open Source Development in practice**

AWS Hero Johannes Koch, together with fellow AWS Hero Thorsten Höger and AWS Community Builder Raphael Manke, take a look at implementing projen pipelines, a new project that  Thorsten and Johannes started recently, hat empowers developers to switch between different CI/CD systems easily.

{{< youtube 5o2-aEo-h-k >}}

**FOSS in Flux: Redis Relicensing and the Future of Open Source**

David Nalley from AWS chats with Dotan Horovits about all things open source, covering a number of topics including the recent license changes to Redis, what this means to its users, and a look at how we think of open source at AWS.

{{< youtube WV0ESadKuVI >}}

**The New Builders: Tom Callaway talks about Building OSS Culture at AWS**

My good friend Spot discusses building open source culture at AWS with Rachel Stephens of RedMonk. Learn more about AWS’ open source teams, how AWS thinks about both adopting and releasing open source projects, and some of the ways that they assess project and community health.

{{< youtube m3F4nTtCQBE >}}

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

The Cortex community call happens every two weeks on Thursday, alternating at 1200 UTC and 1700 UTC. You can check out the GitHub project for more details, go to the [Community Meetings](https://github.com/cortexproject/cortex#community-meetings) section. The community calls keep a rolling doc of previous meetings, so you can catch up on the previous discussions. Check the [Cortex Community Meetings Notes](https://docs.google.com/document/d/1shtXSAqp3t7fiC-9uZcKkq3mgwsItAJlH6YW6x1joZo/edit) for more info.

**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://www.meetup.com/OpenSearch/)

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes:  Franck Pachot, Andrew Lee, Vikram Sethi, Saifeddine Rajhi, Randy D, João Galego, Kinnar Kumar Sen, Alex Lines, Mengfei Wang, Jerry Zhang, Elkin Gonzalez, John Scott, Maurits de Groot, Jyri Seiger, Ariq Rahman, Ryan Yanchuleff, Rajdeep Saha, Anil Razdan, Mike Cochran, Pardeep Chahal, Alex Domijan, Rick Kidder, Scott Sizemore, Kevin Sutherland, Bhanu Ganesh Gudivada, Mansi Suratwala, Santhosh Kumar Adapa, Jeevan Shetty, Andrea Caldarone, Ken Hu, Richard Fan,  Achraf Souk, Corneliu Croitoru, and Cristian Graziano.

**Feedback**

Please please please take 1 minute to [complete this short survey](https://www.pulse.aws/promotion/10NT4XZQ). 

### Stay in touch with open source at AWS

Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) for more open source goodness.

One of the pieces of feedback I received in 2023 was to create a repo where all the projects featured in this newsletter are listed. Where I can hear you all ask? Well as you ask so nicely, you can meander over to[ newsletter-oss-projects](https://github.com/094459/newsletter-oss-projects).

Made with ♥ from DevRel
