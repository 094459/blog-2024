---
title: 'AWS open source newsletter #202'
date: '2024-07-22'
tags : [ oss-newsletter, aws open source, PostgreSQL, OpenSearch, Cedar, Kubernetes, Amazon EKS, OpenShift, ROSA, PHP, Flyway, LiteLLM, GraphRAG, Valkey, Finch, Dask, Cilium, Apache Kafka, Grafana, Prometheus, AWS CDK, Trusted Language Extensions for PostgreSQL, MySQL, MariaDB, InfluxDB, Apache Solr, Apache Flink, MLflow, Notation, Amazon Linux 2023, RabbitMQ,   ]
canonicalUrl: "https://community.aws/content/2jugbeGQ2ygPv13UbwhClgWPiZt/aws-open-source-newsletter-202"
---

##  Edition #202

Welcome to the AWS open source newsletter, issue #202. In this edition, I share more new projects (thank you for those of you that have sent them through) which include a project to help you monitor your data pipelines, the open sourced AWS Secrets Manager agent, a really cool new framework for managing multi generative AI agents, a couple of interesting projects to help manage your AWS accounts, a repo that provides CloudFormation snippets, and a few demo applications including one I put together that shows how you can use the Amazon Bedrock Converse API to summarise Hacker News comments.

Once you have taken a look at the projects, there is plenty of reading material this week, with posts covering open source projects including PostgreSQL, OpenSearch, Cedar, Kubernetes,  OpenShift, Flyway, LiteLLM, GraphRAG, Valkey, Finch, Dask, Cilium, Apache Kafka, Grafana, Prometheus, AWS CDK, Trusted Language Extensions for PostgreSQL, MySQL, MariaDB, InfluxDB, Apache Solr, Apache Flink, MLflow, Notation, Amazon Linux 2023, and RabbitMQ. To finish up we have a really great video on Cedar Agent (part of a series of fantastic videos that are a must watch if you are interested in learning more about this project), and I share some upcoming events you might want to put in your diary.

As always, get in touch if you want me to feature your projects in this open source newsletter. Until the next time, I will leave you to dive into the good stuff!

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution. The projects mentioned here do not represent any formal recommendation or endorsement, I am just sharing for greater awareness as I think they look useful and interesting!*

### Tools

**aws-secretsmanager-agent**

[aws-secretsmanager-agent](https://github.com/aws/aws-secretsmanager-agent) is a local HTTP service that you can install and use in your compute environments to read secrets from Secrets Manager and cache them in memory. The Secrets Manager Agent can retrieve and cache secrets in memory so that your applications can consume secrets directly from the cache. That means you can fetch the secrets your application needs from the localhost instead of making calls to Secrets Manager. The Secrets Manager Agent can only make read requests to Secrets Manager - it can't modify secrets. The Secrets Manager Agent uses the AWS credentials you provide in your environment to make calls to Secrets Manager. The Secrets Manager Agent offers protection against Server Side Request Forgery (SSRF) to help improve secret security. You can configure the Secrets Manager Agent by setting the maximum number of connections, the time to live (TTL), the localhost HTTP port, and the cache size.

Check out the README for more details, configuration options, info on logging and some security considerations too.

**salmon**

[salmon](https://github.com/Soname-Solutions/salmon) is a new open source solution from Soname Solutions that provides an alerting solution for your AWS based data pipelines, which has been designed with ease of use in mind. The solution focus' on AWS services such as Glue, Step Functions, EMR, and others. Check out the repo for details on how it works, as well as some examples to get you going. One to try out I think.

![example salmon dashboard in grafana](https://github.com/Soname-Solutions/salmon/blob/main/docs/images/grafana/timestream-dashboard.png?raw=true)

**multi-agent-orchestrator**

[multi-agent-orchestrator](https://github.com/awslabs/multi-agent-orchestrator) is a new open source project that provides a flexible and powerful framework for managing multiple AI agents and handling complex conversations. It intelligently routes queries and maintains context across interactions. The system offers pre-built components for quick deployment, while also allowing easy integration of custom agents and conversation messages storage solutions. This adaptability makes it suitable for a wide range of applications, from simple chatbots to sophisticated AI systems, accommodating diverse requirements and scaling efficiently. This project has rather nifty documentation too, which you can check out [here](https://awslabs.github.io/multi-agent-orchestrator/deployment/demo-web-app/).

![overview of multi-agent-orch flow](https://github.com/awslabs/multi-agent-orchestrator/blob/main/img/flow.jpg?raw=true)

**aft-account-suspend-close-solution**

[aft-account-suspend-close-solution](https://github.com/aws-samples/aft-account-suspend-close-solution) provides a sample solution that leverages AWS Control Tower Account Factory Terraform (AFT) to streamline the account closure and suspension process. The solution aims to provide a reliable, efficient, and fast way to manage the decommissioning of AWS accounts from organisations.

![overview of solution architecture of aft-account-suspend](https://github.com/aws-samples/aft-account-suspend-close-solution/blob/main/Images/aft-acc-close.png?raw=true)

**integrate-control-tower-with-ipam**

[integrate-control-tower-with-ipam](https://github.com/aws-samples/integrate-control-tower-with-ipam) This project implements a solution which integrates Amazon IP Address Management (IPAM) within AWS Control Tower through the use of Lifecycle Events. It presents the architecture view and shows how this solution extends your AWS Control Tower environment with Amazon IPAM to allow teams to access IPAM pools for their workload accounts.

**orgs-prescriptive-guidance**

[orgs-prescriptive-guidance](https://github.com/aws-samples/orgs-prescriptive-guidance) This repository contains a collection of AWS CloudFormation templates to create up an AWS Organizations structure. So if you are looking to implement this, or are curious and want to dig into the code to find out more, check out this repo.


**security-hub-compliance-analyzer**

[security-hub-compliance-analyzer](https://github.com/awslabs/security-hub-compliance-analyzer) this repo provides a compliance analysis tool which enables organisations to more quickly articulate their compliance posture and also generate supporting evidence artefacts. Security Hub Compliance Analyzer (SHCA) generates artefacts in support of Department of Defense Risk Management Framework (RMF) Information System accreditation. Utilising Amazon Web Services provided documentation, mapping NIST800-53-Rev-5 Controls to AWS Security Hub Security Control IDs, SHCA requests the current environment compliance from Security Hub and generates a zip file stored in Amazon S3 containing discrete artefacts in CSV, JSON, OCSF providing SecOps with artefacts to import into the RMF tool.

![overview of shca solution architecture](https://github.com/awslabs/security-hub-compliance-analyzer/blob/main/images/shca_diagram.png?raw=true)

**awsid**

[awsid](https://github.com/ak2-au/awsid) is the latest novel project from Aidan Steele, author of many curiosities in the past, and this time (using his own words) he has created a tool that is "an incredibly niche tool, that might be of interest to half a dozen people. It turns AWS unique IDs into ARNs. I used generative AI to generate the UI." Check it out and see if you are part of that niche! (also make sure you check out the README about what he can potentially see)

### Demos, Samples, Solutions and Workshops

**hackernews-converse-api-demo**

[hackernews-converse-api-demo](https://github.com/094459/hackernews-converse-api-demo) this repo provides some sample code on how you can use the Amazon Bedrock Converse API, using an example of summarising comments from a Hacker News thread. It is a simple example, but shows you how easy it is to incorporate generative AI in your own applications. You can check out the supporting blog post too, [Save time reading Hacker News comments using Converse API](https://community.aws/content/2jhDpOY0CI1KEhKkk1GFDEYUWHd/save-time-reading-hacker-news-comments-using-converse-api)

**valkey-python-demo**

[valkey-python-demo](https://github.com/094459/valkey-python-demo) provides some sample code that shows you how you can connect to a Valkey server using three different types of client. Existing Redis clients, the Valkey client, and the all new GLIDE client too. I put together a quick blog post on how I put this code together, so check it out - [Using Amazon Q Developer to update Valkey client code](https://community.aws/content/2jSN5k83A5Wayog5Rkin4TmbLhg/using-amazon-q-developer-to-update-valkey-client-code)

**valkey-finch**

[valkey-finch](https://github.com/094459/valkey-finch) is a quick recipe on how to run Valkey in a container using Finch. It did not work out of the box for me, and I had to figure out how to get it working. Now you can save yourself the trouble and check out this configuration. I also put a short blog on this, so check out [Getting started with Valkey and Finch](https://community.aws/content/2jPNz5C31N4dQpeLiDycNNlReCy/getting-started-with-valkey-and-finch)

### AWS and Community blog posts

**This weeks essential reading**

These were my favourite reads since the last newsletter was published. Let me know what you think.

* [Synopsis of several compelling features in PostgreSQL 16](https://aws.amazon.com/blogs/database/synopsis-of-several-compelling-features-in-postgresql-16/) explores the new features in PostgreSQL 16 and discuss how they improve performance and query speed - a must read
* [Simplifying Just-in-Time Access Governance using Cedar](https://www.commonfate.io/blog/jit-using-cedar) find out how you can build a solution to provide just in time authorisation using Cedar
* [Configure SAML federation with Amazon OpenSearch Serverless and Keycloak](https://aws.amazon.com/blogs/big-data/configure-saml-federation-with-amazon-opensearch-serverless-and-keycloak/) shows you how to configure SAML authentication for controlling access to public OpenSearch Dashboards using Keycloak as an IdP [hands on]
AWS Secrets Manager

**What I am reading from around the Community**

Each week I spent a lot of time reading posts from across the AWS community on open source topics. In this section I share what personally caught my eye and interest, and  I hope that many of you will also find them interesting. 

Starting this issue's round up is [AWS: Kubernetes and Access Management API, the new authentication in EKS ](https://dev.to/aws-builders/aws-kubernetes-and-access-management-api-the-new-authentication-in-eks-1hkd) from AWS Community Builder Arseny Zinchenko which explores how the Amazon EKS service authenticates and authorises users (both actual users as well as Worker Nodes). This topic is foundational knowledge, so its worth keeping up with how this works. Sticking with Kubernetes we have AWS Community Builder Marco Gonzalez who has put together, [Building your first ROSA🌹 with Red Hat and AWS](https://dev.to/aws-builders/building-your-first-rosa-with-red-hat-and-aws-3jjd) that provides a gentle and hands on introduction into OpenShift. If you were looking to know more, why not check out this post.

It has been a while since I have featured PHP content, and the PHP developer community are still very much alive, well, and relevant as I found out last week whilst in attendance at WeAreDevelopers. So AWS Community Builder Rafael Araújo is providing the PHP goodies and shares how you can cache secrets within your PHP serverless applications in the post, [Cached SSM and Secrets Values for PHP Lambda on CDK](https://community.aws/content/2j2e52CPCE1MG9wT1tb4d5KlwmC/cached-ssm-and-secrets-values-for-php-lambda-on-cdk). Flyway is a well known open source project that helps developers manage deployments to their SQL databases, and AWS Community Builder Nathan (Nursultan) Bekenov has put together a series of posts, starting with [Run Flyway DB migrations with AWS Lambda and RDS - Part 1](https://dev.to/aws-builders/run-flyway-db-migrations-with-aws-lambda-and-rds-part-1-2a6j) that shows how you can use it with your Amazon RDS databases.

Moving onto generative AI, we have a couple of very cool posts covering the topic of graph data and Retrieval-Augmented Generation (RAG). João Galego shares how to run GraphRAG pipelines backed by Amazon Bedrock using LiteLLM proxy in his post, [Hacking GraphRAG with Amazon Bedrock](https://community.aws/content/2j0H7GskVBBq4UJznR0GEtVIeV8/everything-s-a-graph-hacking-graphrag-with-amazon-bedrock). Don't worry if you are unfamiliar with GraphRAG as Joao walks you through everything in details, providing good explanations as well as supporting code to help you get started. Following that post we have [Build a GraphRAG proof of concept](https://community.aws/content/2fbDaroTl5DlP2KYECrsdmvwAG3/build-a-graphrag-proof-of-concept) from Anand Komandooru, that covers similar territory but this time also shows you how you can use Amazon Neptune as your source graph data.

Closing things up for this issue we have [Simplifying Just-in-Time Access Governance using Cedar](https://www.commonfate.io/blog/jit-using-cedar) from Rowan Udell, who shares how you can build a solution to provide just in time authorisation using Cedar. Very cool post. Last but not least is a post I put together last week whilst working on the Valkey booth at WeAreDevelopers, showing you how you can get started with the Valkey with Finch. As regular readers will know, I have switch from Docker Desktop to Finch since 2024, and am finding it works really well. Occasionally you do run into issues, as I found when trying to get a local instance of Valkey up and running. So if you want to know how and bypass all the huffing and puffing I went through, go check [Getting started with Valkey and Finch](https://community.aws/content/2jPNz5C31N4dQpeLiDycNNlReCy/getting-started-with-valkey-and-finch).

**Cloud Native**

* [Gang scheduling pods on Amazon EKS using AWS Batch multi-node processing jobs](https://aws.amazon.com/blogs/hpc/gang-scheduling-pods-on-amazon-eks-using-aws-batch-multi-node-processing-jobs/) provides a walk through on how to use AWS Batch MNP jobs to set up a Dask distributed processing job on EKS [hands on]
* [Developer’s Guide to operate game servers on Kubernetes – Part 1](https://aws.amazon.com/blogs/gametech/developers-guide-to-operate-game-servers-on-kubernetes-part-1/) is the first in a series of posts that provides you with fundamental knowledge to improve the creation of Kubernetes clusters for games [hands on]
* [Getting Started with Cilium Service Mesh on Amazon EKS](https://aws.amazon.com/blogs/opensource/getting-started-with-cilium-service-mesh-on-amazon-eks/) explains how to deploy Cilium Service Mesh as Kubernetes Ingress and how to leverage it to shift traffic using Envoy based Layer 7 aware traffic policies [hands on]

![overview of cilium components when deployed](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2024/07/16/Cilium_Components1.png)

* [Harnessing Karpenter: Transitioning Kafka to Amazon EKS with AWS solutions](https://aws.amazon.com/blogs/containers/harnessing-karpenter-transitioning-kafka-to-amazon-eks-with-aws-solutions/) shares the key benefits that one organisation found when moving their Kafka applications to Kubernetes, the challenges they faced, and the AWS solutions adopted to overcome those challenges [hands on]
* [Centralize observability with Amazon Managed Grafana Enterprise plugins](https://aws.amazon.com/blogs/mt/centralize-observability-with-amazon-managed-grafana-enterprise-plugins/) walks you through what Grafana Enterprise plugins are and how they can help you simplify your reporting dashboards
* [Enhance your SAP Observability using Amazon Managed Prometheus and Grafana](https://aws.amazon.com/blogs/awsforsap/enhance-your-sap-observability-using-amazon-managed-prometheus-and-amazon-managed-grafana/) looks at how to setup SAP observability dashboards for an SAP S/4HANA system using Amazon Managed Prometheus and Amazon Managed Grafana [hands on]
* [Accelerating development feedback loops with AWS CDK hotswap deployments for Amazon ECS](https://aws.amazon.com/blogs/containers/accelerating-development-feedback-loops-with-aws-cdk-hotswap-deployments-for-amazon-ecs/) provides a case study on how one customer was able to use AWS CDK pipelines to "hotswap" Amazon ECS deployments and accelerate their developer feedback loops [hands on]

**PostgreSQL**

We had lots of great Postgres related posts over the past few weeks, here are some of the ones that stood out for me:

* [Implement UUIDv7 in Amazon RDS for PostgreSQL using Trusted Language Extensions](https://aws.amazon.com/blogs/database/implement-uuidv7-in-amazon-rds-for-postgresql-using-trusted-language-extensions/) looks at how with the help of Trusted Language Extensions for PostgreSQL (pg_tle), you can start using UUIDv7 via the pg_uuidv7 PostgreSQL C extension [hands on] 
* [Migrate an Amazon QLDB Ledger to Amazon Aurora PostgreSQL](https://aws.amazon.com/blogs/database/migrate-an-amazon-qldb-ledger-to-amazon-aurora-postgresql/) demonstrates a process for migrating an Amazon QLDB ledger into Amazon Aurora PostgreSQL using a well known sample database, which you can use as the basis for your own migration [hands on]
* [Replace Amazon QLDB with Amazon Aurora PostgreSQL for audit use cases](https://aws.amazon.com/blogs/database/replace-amazon-qldb-with-amazon-aurora-postgresql-for-audit-use-cases/) shares how to use Amazon Aurora PostgreSQL-Compatible Edition as an alternative to Amazon QLDB for auditing and what features of Amazon Aurora PostgreSQL can replace some of the unique capabilities offered by Amazon QLDB
* [Index types supported in Amazon Aurora PostgreSQL and Amazon RDS for PostgreSQL (GIN, GiST, HASH, BRIN)](https://aws.amazon.com/blogs/database/index-types-supported-in-amazon-aurora-postgresql-and-amazon-rds-for-postgresql-gin-gist-hash-brin/) and [Index types supported in Amazon Aurora PostgreSQL and Amazon RDS for PostgreSQL (B-tree) ](https://aws.amazon.com/blogs/database/index-types-supported-in-amazon-aurora-postgresql-and-amazon-rds-for-postgresql-b-tree/)takes a look at  some of the native indexes supported in Amazon Aurora PostgreSQL-Compatible Edition, with some guidance on how/when to use them [hands on]

**Other posts to check out**

* [Export Amazon RDS for MySQL and MariaDB databases to Amazon S3 using a custom API](https://aws.amazon.com/blogs/database/export-amazon-rds-for-mysql-and-mariadb-databases-to-amazon-s3-using-a-custom-api/) shows how a DBA or other user with access to a custom API can make MySQL and MariaDB backup requests [hands on]

![overview of solution flow and architecture](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2024/07/23/DBBLOG-2735_architecturev2.png)

* [Use the AWS InfluxDB migration script to migrate your InfluxDB OSS 2.x data to Amazon Timestream for InfluxDB](https://aws.amazon.com/blogs/database/use-the-aws-influxdb-migration-script-to-migrate-your-influxdb-oss-2-x-data-to-amazon-timestream-for-influxdb/) demonstrates how to use the AWS InfluxDB migration script to migrate your data from your existing InfluxDB OSS 2.x instances to Timestream for InfluxDB [hands on]
* [LLM experimentation at scale using Amazon SageMaker Pipelines and MLflow](https://aws.amazon.com/blogs/machine-learning/llm-experimentation-at-scale-using-amazon-sagemaker-pipelines-and-mlflow/) explores how you can use Amazon SageMaker with MLflow to dive into LLM customisation using fine-tuning and some of the considerations for successful experimentation [hands on]

![overview of solution architecture ](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2024/07/17/ml-16670-llm-selection-journey.png) 

* [Migrate from Apache Solr to OpenSearch](https://aws.amazon.com/blogs/big-data/migrate-from-apache-solr-to-opensearch/) is just what you need if you currently use Apache Solr, and are looking to migrate to something else - in this instance, OpenSearch [hands on]
* [How PostNL processes billions of IoT events with Amazon Managed Service for Apache Flink](https://aws.amazon.com/blogs/big-data/how-postnl-processes-billions-of-iot-events-with-amazon-managed-service-for-apache-flink/) describes the legacy PostNL stream processing solution, its challenges, and why PostNL chose Apache Flink to help modernise their Internet of Things (IoT) data stream processing platform

![new architecture using apache flink at postnl](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2024/07/10/BDB-4162-3-testing_architecture-2.png)

### Quick updates

**Kubernetes**

Amazon EKS announced new controls for Kubernetes version policy, allowing cluster administrators to configure end of standard support behaviour for EKS clusters. This behaviour can easily be set through the EKS Console and CLI. Kubernetes version policy control is available for Kubernetes versions in standard support. Controls for Kubernetes version policy makes it easier for you to choose which clusters should enter extended support and which clusters can be automatically upgraded at the end of standard support. This control provides the flexibility for you to balance version upgrades against business requirements depending on the environment or applications running per cluster. Controls for Kubernetes version policy is available in all AWS regions.

**Notation**

AWS open-sourced the AWS Signer plugin for Notation, giving customers flexibility and transparency in how they sign and verify container images with AWS Signer, a managed signing service. Notation is an open source tool developed by the Notary Project, an industry standard for securing software supply chains by authenticating container images and other OCI artefacts. The plugin extends Notation with Signer managed secrets and revocation capabilities. Customers can now incorporate the Signer plugin as a library inside their native tools to generate and verify container artefacts signatures. Notation can be used as a CLI executable or as a Golang library. With the open sourced Signer Plugin, you can now seamlessly incorporate signing and verification activities into your existing applications and tooling by adding a go-library. This removes the need for installing and invoking the plugin as an executable. Additionally, you get transparency in how AWS Signer APIs are used for signature generation and verification. If you prefer a CLI integration with Signer, you can now also build your own version of the Signer Plugin executable or continue downloading pre-built executables from AWS Signer documentation. AWS Signer Plugin is released as an open-source project under the Apache 2.0 license.

Read more about this by checking out the blog from Jimmy Ray and Jesse Butler, [Announcing Container Image Signing with AWS Signer and Amazon EKS](https://aws.amazon.com/blogs/containers/announcing-container-image-signing-with-aws-signer-and-amazon-eks/) and review the code in the GitHub repo [aws-signer-notation-plugin](https://github.com/aws/aws-signer-notation-plugin)

**Amazon Linux 2023**

Amazon Elastic Container Service (Amazon ECS) now supports managing on-premises workloads running on Amazon Linux 2023, Fedora 40, Debian 11, Debian 12, Ubuntu 24, and CentOS Stream 9. Amazon ECS Anywhere is a feature of Amazon ECS that enables you to run and manage container-based applications on-premises, including on your own virtual machines (VMs) and bare metal servers.

**RabbitMQ**

Amazon MQ now provides support for quorum queues, a replicated FIFO queue type offered by open-source RabbitMQ that uses the Raft consensus algorithm to maintain data consistency. Quorum queues are the replicated queue type recommended by open-source RabbitMQ maintainers. With quorum queues, developers can design highly available messaging systems with higher data consistency and fault tolerance. Quorum queues can detect network failures faster and recover more quickly, improving the resiliency of the message broker as a whole. Quorum queues also provide poison message handling which helps developers manage unprocessed messages more efficiently. Amazon MQ benchmarks show that quorum queues offer an increased throughput (up to 2 times higher) compared to classic mirrored queues on RabbitMQ brokers. Amazon MQ supports quorum queues only on RabbitMQ 3.13 and above. You can easily get started with quorum queues by declaring a new queue with queue type as ‘quorum’. 

Check out [Introducing quorum queues on Amazon MQ for RabbitMQ](https://aws.amazon.com/blogs/compute/introducing-quorum-queues-on-amazon-mq-for-rabbitmq/) where Vignesh Selvam and  Simon Unge share an overview of what quorum queues are

**MySQL**

The Amazon Web Services (AWS) Advanced MySQL ODBC driver has been released as an open-source project under version 2 of the GNU General Public License (GPL v2). The AWS ODBC Driver for MYSQL is now generally available for use with Amazon RDS and Amazon Aurora MySQL-compatible edition database clusters. This database driver provides support for faster switchover and failover times, and authentication with AWS Secrets Manager or AWS Identity and Access Management (IAM). The Amazon Web Services (AWS) ODBC Driver for MYSQL is a standalone driver and supports RDS and community MySQL 8.X and Amazon Aurora MySQL version 3.X. You can install the aws-mysql-odbc package for Windows, Mac or Linux by following established installation guides in GitHub. The driver relies on monitoring the database cluster status and being aware of the cluster topology to determine the new writer. This approach reduces switchover and failover times from tens of seconds to single digit seconds compared to the open-source driver.

**MariaDB**

Amazon RDS for MariaDB now supports version 11.4 in the Amazon RDS Database Preview Environment, allowing you to evaluate the latest Long-Term Support Release on Amazon RDS for MariaDB. You can deploy MariaDB 11.4 in the Amazon RDS Database Preview Environment that has the benefits of a fully managed database, making it simpler to set up, operate, and monitor databases. MariaDB 11.4 is the latest Long-Term Support Release from the MariaDB community. MariaDB Long-Term Support Releases include bug fixes, security patches, as well as new features. Please refer to the MariaDB 11.4 release notes for more details about this release. The Amazon RDS Database Preview Environment supports both Single-AZ and Multi-AZ deployments on the latest generation of instance classes. Amazon RDS Database Preview Environment database instances are retained for a maximum period of 60 days and are automatically deleted after the retention period. Amazon RDS database snapshots that are created in the preview environment can only be used to create or restore database instances within the preview environment.


### Videos of the week

**Cedar Agent: Use Cedar Everywhere!**

This series of short videos on all things Cedar is a must watch for all developers who are looking to implement authorisation with Cedar. This time the video is on Cedar Agent. Cedar Agent lets you "sidecar" Cedar in for any application, even in languages or frameworks that don't otherwise provide Cedar bindings! In this video you will learn the big picture of how Cedar Agent can fit into your design and highlight how quick and easy it is to get up and running. Finally, because Cedar Agent lets your register a Cedar schema, it can even check each request to help find errors early.

{{< youtube OX3rNuA5zWU >}}

### Events for your diary

If you are planning any events in 2024, either virtual, in person, or hybrid, get in touch as I would love to share details of your event with readers. 

**Open Source Summit**
**September 16-18th, Vienna, Austria**

Come join my colleagues at the AWS booth at the Open Source Summit Europe, which is being held in the wonderful city of Vienna. There will be a bunch of around, doing talks, open source technology demos, and just hanging out with the open source community. Be great to see some of you there.

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

So thank you to the following open source heroes: Anatolii Maslov, Vignesh Selvam,  Simon UngeAnthony Leung, Trevor Bonas, Jagdeep Singh Soni, Kirit Thadaka, Piyush Kadam, Sokratis Kartakis, Arpad Csoke, Marcos Freccia, Fabian Jahnke,  Angel Pizarro, Aswath Srinivasan, Jon Handler, Dan Blaner, Serge Poueme, Badrish Shanbhag, Marcos Hauer, Scott Flaster, Dumlu Timuralp, Bijith Nair, Piotr Jablonski, Praseeda Sathaye,  Sachin Khanna, Rajkumar Raghuwanshi, Sachin Kotwal, Alicia Plotnikov, Eitav Arditti, Tom Wright, Abhaya Chauhan, Yogesh Pillai, Arun Chandapillai, Mengdi Chen, Priyanka Verma, Ravi Kashyap, Rutvij Dave, Çağrı Çakır, Ozge Kavalci, Amit Singh, Lorenzo Nicora, Jonathan Katz, Rajesh Madiwale, Baji Shaik, Swanand Kshirsagar, Rowan Udell, João Galego, Anand Komandooru, Nathan (Nursultan) Bekenov, Rafael Araújo, Marco Gonzalez, Arseny Zinchenko, Jimmy Ray and Jesse Butler

**Feedback**

Please please please take 1 minute to [complete this short survey](https://www.pulse.aws/promotion/10NT4XZQ). 

### Stay in touch with open source at AWS

Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) for more open source goodness.

One of the pieces of feedback I received in 2023 was to create a repo where all the projects featured in this newsletter are listed. Where I can hear you all ask? Well as you ask so nicely, you can meander over to[ newsletter-oss-projects](https://github.com/094459/newsletter-oss-projects).

Made with ♥ from DevRel
