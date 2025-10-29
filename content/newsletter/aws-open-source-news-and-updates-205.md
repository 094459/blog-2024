---
title: 'AWS open source newsletter #205'
date: '2024-11-30'
tags : [ oss-newsletter, aws open source,  AWS CDK, Amazon EKS, Kubernetes, Apache Iceberg, Dapr, Lustre, kro, Projen, ComfyUI, Finch, Open Cybersecurity Schema Framework, OCSF, PostgreSQL, Amazon EMR, Apache Cassandra, MySQL, HBase, AWS Amplify, Apache XTable, Mountpoint for Amazon S3, Valkey, Apache Airflow, MWAA, Bottlerocket, Apache Kafka, Apache Flink]
canonicalUrl: "https://community.aws/content/2pbgDjylg23XWvy5RpWZ3BcsoNA/aws-open-source-newsletter-205"
---

Welcome to issue #205 of the AWS open source newsletter, the newsletter where we try and provide you the best open source on AWS content.  This will be the last edition of 2024, but looking forward to coming back in 2025 with more great open source project and content. As always, we have more great new projects to check out, which include a project that simplifies how you manage complex Kubernetes resource configurations, a library to accelerate open source analytics using Amazon S3, a look at a GraphRAG project, a project that helps NodeJS developers make it easier to make use of some advanced Amazon Aurora capabilities, an ESLinting tool for AWS CDK, and more. 

Also featured in this edition is content on some of your (and mine) favourite open source projects, which include AWS CDK, Kubernetes, Apache Iceberg, Dapr, Lustre, kro, Projen, ComfyUI, Finch, Open Cybersecurity Schema Framework, PostgreSQL, Amazon EMR, Apache Cassandra, MySQL, HBase, AWS Amplify, Apache XTable, Mountpoint for Amazon S3, Valkey, Apache Airflow, Bottlerocket, Apache Kafka, and Apache Flink. That lot should keep you busy until the new year!

As always, get in touch if you want me to feature your projects in this open source newsletter. Until the next time, I will leave you to dive into the good stuff!

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution. The projects mentioned here do not represent any formal recommendation or endorsement, I am just sharing for greater awareness as I think they look useful and interesting!*

### Tools

**kro**

[kro](https://github.com/awslabs/kro) This project aims to simplify the creation and management of complex custom resources for Kubernetes. Kube Resource Orchestrator (kro) provides a powerful abstraction layer that allows you to define complex multi-resource constructs as reusable components in your applications and systems. You define these using kro's fundamental custom resource, ResourceGroup. This resource serves as a blueprint for creating and managing collections of underlying Kubernetes resources. With kro, you define custom resources as your fundamental building blocks for Kubernetes. These building blocks can include other Kubernetes resources, either native or custom, and can specify the dependencies between them. This lets you define complex custom resources, and include default configurations for their use. The kro controller will determine the dependencies between resources, establish the correct order of operations to create and configure them, and then dynamically create and manage all of the underlying resources for you. kro is Kubernetes native and integrates seamlessly with existing tools to preserve familiar processes and interfaces.

**analytics-accelerator-s3**

[analytics-accelerator-s3](https://github.com/awslabs/analytics-accelerator-s3) the Analytics Accelerator Library for Amazon S3 is an open source library that accelerates data access from client applications to Amazon S3. With this tool you can 1/ lower processing times and compute costs for data analytics workloads, 2/ implement S3 best practices for performance, 3/utilise optimisations specific to Apache Parquet files, such as pre-fetching metadata located in the footer of the object and predictive column pre-fetching, and 4/improve the price performance for your data analytics applications, such as workloads based on Apache Spark.

Project is currently in Alpha, so bear that in mind. More examples and details in the README.

**graphrag-toolkit**

[graphrag-toolkit](https://github.com/awslabs/graphrag-toolkit) is a Python toolkit for building GraphRAG applications. It provides a framework for automating the construction of a graph from unstructured data, and composing question-answering strategies that query this graph when answering user questions. The toolkit uses low-level LlamaIndex components – data connectors, metadata extractors, and transforms – to implement much of the graph construction process. By default, the toolkit uses Amazon Neptune Analytics or Amazon Neptune Database for its graph store, and Neptune Analytics or Amazon OpenSearch Serverless for its vector store, but it also provides extensibility points for adding alternative graph stores and vector stores. The default backend for LLMs and embedding models is Amazon Bedrock; but, as with the stores, the toolkit can be configured for other LLM and embedding model backends using LlamaIndex abstractions.

**aws-advanced-nodejs-wrapper**

[aws-advanced-nodejs-wrapper](https://github.com/aws/aws-advanced-nodejs-wrapper) is complementary to an existing NodeJS driver and aims to extend the functionality of the driver to enable applications to take full advantage of the features of clustered databases such as Amazon Aurora.  In other words, the AWS Advanced NodeJS Wrapper does not connect directly to any database, but enables support of AWS and Aurora functionalities on top of an underlying NodeJS driver of the user's choice.

Hosting a database cluster in the cloud via Aurora is able to provide users with sets of features and configurations to obtain maximum performance and availability, such as database failover. However, at the moment, most existing drivers do not currently support those functionalities or are not able to entirely take advantage of it. The main idea behind the AWS Advanced NodeJS Wrapper is to add a software layer on top of an existing NodeJS driver that would enable all the enhancements brought by Aurora, without requiring users to change their workflow with their databases and existing NodeJS drivers.

Check out the README for additional details on how this simplifies life for developers wanting to access those advanced features.

**amazon-q-developer-cli**

[amazon-q-developer-cli](https://github.com/aws/amazon-q-developer-cli) is the repo that houses most of the core code for the Amazon Q Developer desktop app and CLI, adding autocomplete and AI to your existing terminal on macOS & Linux.

**eslint-cdk-plugin**

[eslint-cdk-plugin](https://github.com/ren-yamanashi/eslint-cdk-plugin) provides an ESLint plugin for AWS CDK. ESLint is a static code analysis tool for identifying problematic patterns found in JavaScript code. This provides rules for the AWS CDK to help you write readable, maintainable, and reusable code. There are extensive rules provided ([eslint-rules](https://github.com/cdklabs/eslint-rules)) to get you going. Check out the project webpage [here](https://eslint-cdk-plugin.dev/).

**Drag-and-Drop-Email-Designer**

[Drag-and-Drop-Email-Designer](https://github.com/SendWithSES/Drag-and-Drop-Email-Designer) looks like a neat project that provides a way of designing email templates that you can use with the Send with SES project. Check out the README for some visuals on what this looks like.

### Demos, Samples, Solutions and Workshops

**fmbench-orchestrator**

[fmbench-orchestrator](https://github.com/awslabs/fmbench-orchestrator) this repo is a tool designed to automate the deployment and management of FMBench for benchmarking on Amazon EC2, Amazon SageMaker and Amazon Bedrock. In case of benchmarking on EC2, we could benchmark on multiple instances simultaneously, and these instances can be of different instance types (so you could run g6e, p4de and a trn1 instances via the same config file), in different AWS regions and also test multiple FMBench config files. This orchestrator automates the creation of Security Groups, Key Pairs, EC2 instances, runs FMBench for a specific config, retrieves the results, and shuts down the instances after completion. Thus it simplifies the benchmarking process (no more manual creation of SageMaker Notebooks, EC2 instances and cleanup, downloading results folder) and ensures a streamlined and scalable workflow. Very detailed README that provides much more details on how this works.

**terraform-f1-telemetry-infra**

[terraform-f1-telemetry-infra](https://github.com/majdi-d/terraform-f1-telemetry-infra) this project aims to develop a UDP listener to capture, parse, and visualise this data in real-time using various AWS services, including ECS, Elastic Load Balancing, and Route 53. A number of racing games on leading consoles provide the ability to send telemetry data to a target IP address, which this project will then ingest. Very cool stuff.


### AWS and Community blog posts

Each week I spent a lot of time reading posts from across the AWS community on open source topics. In this section I share what personally caught my eye and interest, and I hope that many of you will also find them interesting.

Starting things off in this edition is AWS Community Builder Claudio Taverna who has put together [Hands-on introduction to Apache Iceberg](https://dev.to/aws-builders/hands-on-introduction-to-apache-iceberg-2hd2) which provides a good primer if you want to know about this very hot open source technology. If you work with data, you will need to know about Apache Iceberg so I recommend folk read this post.  Following that are two posts from AWS Community Builder Omid Eidivandi covering AWS CDK. In [Personal Use of AWS Organizations Using CDK](https://dev.to/aws-builders/personal-use-of-aws-organizations-using-cdk-5b55) and [Conventional Use of AWS CDK](https://dev.to/aws-builders/conventional-use-of-aws-cdk-g0m) where he shares both his experiences as well as some practical source code on how he sets up CDK for different use cases. 

In [Deploying AWS EKS with Terraform and Blueprints Addons](https://dev.to/aws-builders/deploying-aws-eks-with-terraform-and-blueprints-addons-5am6) AWS Community Builder Timur Galeev guides you through using Terraform to deploy EKS with essential add-ons, which streamline the configuration and management of your Kubernetes clusters. Sticking with Kubernetes, we have a couple of posts from AWS Community Builder Saifeddine Rajhi. In his first post, he shares knowledge about k8s-pvc-tagger , a Kubernetes utility that automates the tagging of AWS EBS volumes, in his post [k8s-pvc-tagger: The Swiss Army Knife of AWS EBS Tagging](https://dev.to/aws-builders/k8s-pvc-tagger-the-swiss-army-knife-of-aws-ebs-tagging-51n1). Remember folks, if you don't tag your Cloud resources, do they even exist? Following that he takes a look at Dapr on Kubernetes in his post, [Speed Up Microservices Development with Dapr on AWS EKS](https://dev.to/aws-builders/speed-up-microservices-development-with-dapr-on-aws-ek-85l). Dapr is a very interesting open source project that aims to simplify how you build distributed applications at scale. Definitely a must read this week.

To close this community round up we have JS Labonte who has put together [Build a multi-region FSx for Lustre file system for disaster recovery](https://community.aws/content/2olUWR7GONs9b4qhWHY4TR07L63/build-a-multi-region-fsx-for-lustre-file-system-for-disaster-recovery) where he shares how you can handle failure and maintain service availability even when an entire region or data center goes down, by replicating data, services, and infrastructure across multiple regions.

**This weeks essential reading**

(there were more than usual, as it has been a few weeks since the last newsletter!)

* [Introducing kro: Kube Resource Orchestrator](https://aws.amazon.com/blogs/opensource/introducing-open-source-kro-kube-resource-orchestrator/) looks at this new experimental open source project from AWS that simplifies and empowers the use of custom APIs and resources with Kubernetes [hands on]
* [How to build custom nodes workflow with ComfyUI on Amazon EKS](https://aws.amazon.com/blogs/architecture/how-to-build-custom-nodes-workflow-with-comfyui-on-amazon-eks/) builds on from some earlier posts and sample code, and shows how you can deploy the ComfyUI project on Amazon EKS [hands on]
* [Enhancing Developer Productivity: Finch’s Support for Development Containers and the Finch Daemon](https://aws.amazon.com/blogs/opensource/enhancing-developer-productivity-finchs-support-for-development-containers-and-the-finch-daemon/) looks at some additional capabilities of Finch that will now allow Finch users to use it with VSCode dev containers, as well as the Finch demon which will help improve compatibility as you look to migrate off Docker [hands on]
* [Diving Deeper into Projen: Exploring Advanced Features](https://aws.amazon.com/blogs/devops/diving-deeper-into-projen-exploring-advanced-features/) is a follow up from a previous post (also featured in an earlier version of this newsletter) that looks at some of the more advanced capabilities that help improve developers experience and productivity
* [OCSF Joins the Linux Foundation: Accelerating the Standardization of Cybersecurity Data](https://aws.amazon.com/blogs/opensource/ocsf-joins-the-linux-foundation-accelerating-the-standardization-of-cybersecurity-data/) shares more details about the recent move to the Linux Foundation for the Open Cybersecurity Schema Framework (OCSF), and what it means going forward
* [Amazon Aurora PostgreSQL Limitless Database is now generally available](https://aws.amazon.com/blogs/aws/amazon-aurora-postgresql-limitless-database-is-now-generally-available/) looks at a new serverless horizontal scaling (sharding) capability of Amazon Aurora called Aurora PostgreSQL Limitless Database, where you can scale beyond the existing Aurora limits for write throughput and storage by distributing a database workload over multiple Aurora writer instances while maintaining the ability to use it as a single database [hands on]

**Cloud Native**

* [Disposition strategy and planning for migrating Kubernetes clusters](https://aws.amazon.com/blogs/migration-and-modernization/disposition-strategy-and-planning-for-migrating-kubernetes-clusters/) provides some great insights into a perhaps all to little discussed topic - how you manage your infrastructure resources as you update and migrate your Kubernetes clusters
* [Amazon EKS now supports Amazon Application Recovery Controller](https://aws.amazon.com/blogs/containers/amazon-eks-now-supports-amazon-application-recovery-controller/) demonstrates how you can use the ARC zonal shift and zonal autoshift capabilities to prepare for and recover from AWS Region or Availability Zone (AZ) impairments [hands on]
* [Amazon EKS enhances Kubernetes control plane observability](https://aws.amazon.com/blogs/containers/amazon-eks-enhances-kubernetes-control-plane-observability/) looks at some new control plane observability enhancements to the Amazon EKS clusters [hands on]


**Data and Data Analytics**

* [Run high-availability long-running clusters with Amazon EMR instance fleets](https://aws.amazon.com/blogs/big-data/run-high-availability-long-running-clusters-with-amazon-emr-instance-fleets/) helps you learn how to launch a high availability instance fleet cluster using the newly redesigned Amazon EMR console [hands on]
* [MultiXacts in PostgreSQL: usage, side effects, and monitoring](https://aws.amazon.com/blogs/database/multixacts-in-postgresql-usage-side-effects-and-monitoring/) dives deep into the inner workings of MultiXacts, a special structure within PostgreSQL that relies upon when multiple transactions attempt to lock the same row simultaneously [hands on]
* [Benchmark Amazon RDS for PostgreSQL with Dedicated Log Volumes](https://aws.amazon.com/blogs/database/benchmark-amazon-rds-for-postgresql-with-dedicated-log-volumes/) guide you through the process of benchmarking the performance of Amazon RDS for PostgreSQL using the Dedicated Log Volume (DLV) feature that is available in Amazon RDS - if you are a heavy user of PostgreSQL, this is a must read post [hands on]
* [Load vector embeddings up to 67x faster with pgvector and Amazon Aurora](https://aws.amazon.com/blogs/database/load-vector-embeddings-up-to-67x-faster-with-pgvector-and-amazon-aurora/) provides another great benchmarking post, this time looking at the index build and query times of the new version of pgvector 0.7.0 with the prior [hands on]
* [Optimize Amazon Aurora PostgreSQL auto scaling performance with automated cache pre-warming](https://aws.amazon.com/blogs/database/optimize-amazon-aurora-postgresql-auto-scaling-performance-with-automated-cache-pre-warming/) is a great post that show how to improve query performance of a new replica by warming up the cache using pg_prewarm [hands on]
* [Visualize vector embeddings stored in Amazon Aurora PostgreSQL and explore semantic similarities](https://aws.amazon.com/blogs/database/visualize-vector-embeddings-stored-in-amazon-aurora-postgresql-and-explore-semantic-similarities/) explores how you can gain valuable insights into your data, uncover hidden patterns, and make informed decisions using principal component analysis (PCA) [hands on]

![example 3d graph visualising vector embeddings](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2024/10/18/dbblog-3995-VectorEmbedding_Visual.png)

* [Use Amazon ElastiCache as a cache for Amazon Keyspaces (for Apache Cassandra) ](https://aws.amazon.com/blogs/database/use-amazon-elasticache-as-a-cache-for-amazon-keyspaces-for-apache-cassandra/)  shows you how to use Amazon ElastiCache as a write-through cache for an application that uses an Amazon Keyspaces (for Apache Cassandra) tables [hands on]
* [Best practices for running Apache Cassandra with Amazon EBS](https://aws.amazon.com/blogs/database/best-practices-for-running-apache-cassandra-with-amazon-ebs/) covers how Cassandra interacts with the OS’s file system and page cache when reading from disk, using various Linux tools like iostat, xfsdist, xfsslower, cachestat, and biolatency, to get insights into different layers of disk I/O performance [hands on]
* [Achieve a high-speed InnoDB purge on Amazon RDS for MySQL and Amazon Aurora MySQL](https://aws.amazon.com/blogs/database/achieve-a-high-speed-innodb-purge-on-amazon-rds-for-mysql-and-amazon-aurora-mysql/) looks at how you can improve InnoDB purge efficiency, through  a combination of workload optimisation, database capacity planning, and configurations [hands on]

![graphs showing innodb purge metrics under optinisation](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2024/10/23/DBBLOG-4263-img4.png)

* [Stream real-time data into Apache Iceberg tables in Amazon S3 using Amazon Data Firehose](https://aws.amazon.com/blogs/big-data/stream-real-time-data-into-apache-iceberg-tables-in-amazon-s3-using-amazon-data-firehose/) is a ready to go solution that shows you how to set up Firehose streams to deliver streaming records into Apache Iceberg tables in Amazon S3 [hands on]
* [Apache HBase online migration to Amazon EMR](https://aws.amazon.com/blogs/big-data/apache-hbase-online-migration-to-amazon-emr/) provides some real-world migration cases to introduce the process of migrating HBase to Amazon EMR HBase using HBase snapshot and replication and the deployment mode of HBase on Amazon S3 [hands on]


**Other posts to check out**

* [Build fullstack AI apps in minutes with the new Amplify AI Kit ](https://aws.amazon.com/blogs/mobile/build-fullstack-ai-apps-in-minutes-with-the-new-amplify-ai-kit/) dives into what is in the Amplify AI kit and how it can simplify building secure full-stack AI applications with Amplify and Amazon Bedrock [hands on]
* [Run Apache XTable in AWS Lambda for background conversion of open table formats](https://aws.amazon.com/blogs/big-data/run-apache-xtable-in-aws-lambda-for-background-conversion-of-open-table-formats/) looks at how this emerging open source project helps facilitates seamless conversions between open table formats (OTFs), providing hands on examples and code [hands on]

![solution architecture for apache xtables](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2024/11/16/4-mechanism-detail.png)

* [Amazon FSx for Lustre increases throughput to GPU instances by up to 12x](https://aws.amazon.com/blogs/aws/amazon-fsx-for-lustre-unlocks-full-network-bandwidth-and-gpu-performance/) provides some nice details on how Amazon FSx for Lustre now supports 12 times higher (up to 1200 Gbps) per-client throughput compared to the previous FSx for Lustre version

### Quick updates

**Mountpoint for Amazon S3**

You can now use Amazon S3 Express One Zone as a high performance read cache with Mountpoint for Amazon S3. The cache can be shared by multiple compute instances and can elastically scale to any dataset size. Mountpoint for S3 is a file client that translates local file system API calls to REST API calls on S3 objects. With this launch, Mountpoint for S3 can cache data in S3 Express One Zone after it’s read, making the subsequent read requests up to 7x faster compared to reading data from S3 Standard.

Previously, Mountpoint for S3 could cache recently accessed data in Amazon EC2 instance storage, EC2 instance memory, or an Amazon EBS volume. This improved performance for repeated read access from the same compute instance for dataset sizes up to the size of the available local storage. Starting today, you can also opt in to caching data in S3 Express One Zone, benefiting applications that repeatedly read a shared dataset across multiple compute instances, without any limits on the total dataset size. Once you opt in, Mountpoint for S3 retains objects with sizes up to one megabyte in S3 Express One Zone. This is ideal for compute-intensive use cases such as machine learning training for computer vision models where applications repeatedly read millions of small images from multiple instances.

**PostgreSQL**

There have been a few PostgreSQL related updates since the last newsletter. Here are some of the key ones

* Amazon Relational Database Service (RDS) for PostgreSQL now supports pgvector 0.8.0, an open-source extension for PostgreSQL for storing and efficiently querying vector embeddings in your database, letting you use retrieval-augmented generation (RAG) when building your generative AI applications. pgvector 0.8.0 release includes improvements on PostgreSQL query planner’s selection of index when filters are present, which can deliver better query performance and improve search result quality. pgvector 0.8.0 release includes a variety of improvements to how pgvector filters data using conditions in WHERE clauses and joins that can improve query performance and usability. Additionally, the iterative index scans help prevent ‘overfiltering’, ensuring generation of sufficient results to satisfy the conditions of a query. If an initial index scan doesn't satisfy the query conditions, pgvector will continue to search the index until it hits a configurable threshold. This release also has performance improvements for searching and building HNSW indexes. pgvector 0.8.0 is available on database instances in Amazon RDS running PostgreSQL 17.1 and higher, 16.5 and higher, 15.9 and higher, 14.14 and higher, and 13.17 and higher in all applicable AWS Regions.

* Amazon Relational Database Service (RDS) for PostgreSQL now supports the latest minor versions 17.2, 16.6, 15.10, 14.15, 13.18, and 12.22. We recommend that you upgrade to the latest minor versions to fix known security vulnerabilities in prior versions of PostgreSQL, and to benefit from the bug fixes added by the PostgreSQL community. You are able to leverage automatic minor version upgrades to automatically upgrade your databases to more recent minor versions during scheduled maintenance window. Additionally, starting with PostgreSQL major version 18, Amazon RDS for PostgreSQL will deprecate plcoffee and plls PostgreSQL extensions. We recommend that you stop using Coffee scripts and LiveScript in your applications, ensuring you have an upgrade path for future.

**MySQL**

Amazon RDS for MySQL now supports MySQL major version 8.4, the latest long-term support (LTS) release from the MySQL community. RDS for MySQL 8.4 is integrated with AWS Libcrypto (AWS-LC) FIPS module (Certificate #4816), and includes support for multi-source replication plugin for analytics, Group Replication plugin for continuous availability, as well as several performance and feature improvements added by the MySQL community. Learn more about the community enhancements in the MySQL 8.4 release notes. You can leverage Amazon RDS Managed Blue/Green deployments to upgrade your databases from MySQL 8.0 to MySQL 8.4.

Mershad Irani and Vijay Karumajji have collaborated on the post, [Amazon RDS for MySQL LTS version 8.4 is now generally available](https://aws.amazon.com/blogs/database/amazon-rds-for-mysql-lts-version-8-4-is-now-generally-available/) that looks at this more closely.

**Valkey**

Amazon ElastiCache introduced support for Valkey 8.0, the latest Valkey major version. This release brings faster scaling for ElastiCache Serverless for Valkey and improved memory efficiency on node-based ElastiCache, compared to previous versions of ElastiCache for Valkey and Redis OSS. Valkey is an open-source, high-performance key-value datastore stewarded by the Linux Foundation and is a drop-in replacement for Redis OSS. Backed by over 40 companies, Valkey has seen rapid adoption since its inception in March 2024. ElastiCache Serverless version 8.0 for Valkey scales to 5 million requests per second (RPS) per cache in minutes, up to 5x faster than Valkey 7.2, with microsecond read latency. With node-based ElastiCache, you can benefit from improved memory efficiency, with 32 bytes less memory per key compared to ElastiCache version 7.2 for Valkey and ElastiCache for Redis OSS. AWS has made significant contributions to open source Valkey in the areas of performance, scalability, and memory optimisations, and we are bringing these benefits into ElastiCache version 8.0 for Valkey.

Find out more by checking out the post from Abhay Saxena and Rashim Gupta, [Amazon ElastiCache version 8.0 for Valkey brings faster scaling and improved memory efficiency](https://aws.amazon.com/blogs/database/amazon-elasticache-version-8-0-for-valkey-brings-faster-scaling-and-improved-memory-efficiency/)

In more Valkey news, ElastiCache for Valkey self-designed (node-based) clusters now support server-side write request latency and read request latency metrics. With this launch, you can now measure the server-side response time for Valkey commands and troubleshoot latency spikes in your ElastiCache for Valkey cluster. Monitoring response time is critical to improving end user experience by tracking application trends and adjusting cluster configurations, as needed. The server-side latency metrics provides a complete picture of the server-side response time that includes command pre-processing, command execution, and command post-processing. SuccessfulWriteRequestLatency and SuccessfulReadRequestLatency measure the time that the Valkey engine takes to respond to a successfully executed request.

The final update which came in as I was writing this, is news that the Valkey Glide client 1.2 was released. In this update AWS added support for Availability Zone (AZ) awareness. Valkey GLIDE is a reliable, high-performance, and highly available client, and it’s pre-configured with best practices from over a decade of operating Amazon ElastiCache. Valkey GLIDE is compatible with versions 7.2 and 8.0 of Valkey, as well as versions 6.2, 7.0, and 7.2 of Redis OSS. With this update, Valkey GLIDE will direct requests to Valkey nodes within the same Availability Zone, minimising cross-zone traffic and reducing response time. Java, Python, and Node.js are the currently supported languages for Valkey GLIDE, with further languages in development. With this update, Valkey GLIDE 1.2 also supports Amazon ElastiCache and Amazon MemoryDB’s JavaScript Object Notation (JSON) data type, allowing customers to store and access JSON data within their clusters. In addition, it supports MemoryDB’s Vector Similarity Search, empowering customers to store, index, and search vectors for AI applications at single-digit millisecond speed.

**Apache Airflow**

A couple of updates that I know Apache Airflows are going to love.

First up is news that Amazon Managed Workflows for Apache Airflow (MWAA) now offers a micro environment size, giving customers of the managed service the ability to create multiple, independent environments for development and data isolation at a lower cost. Amazon MWAA is a managed orchestration service for Apache Airflow that makes it easier to set up and operate end-to-end data pipelines in the cloud. With Amazon MWAA micro environments, customers can now create smaller, cost-effective environments that are more efficient for development use, as well as for teams that require data isolation with lightweight workflow requirements. Read [Introducing Amazon MWAA micro environments for Apache Airflow](https://aws.amazon.com/blogs/big-data/introducing-amazon-mwaa-micro-environments-for-apache-airflow/) if you want to know more.

That was cool, but the update that really caught my attention (and is making me want to write something) was the news that Amazon MWAA now supports a simplified mechanism for interacting with the Apache Airflow REST API using AWS credentials. This feature enables customers to programmatically manage and automate workflows, enhancing ease of use and integration capabilities across their Apache Airflow environments. Amazon MWAA is a managed orchestration service for Apache Airflow that makes it easier to set up and operate end-to-end data pipelines in the cloud. With AWS Signature Version 4 (SigV4) support, customers can now integrate MWAA with other AWS and third-party services, and securely interact with the Airflow REST API using their existing AWS credentials. This feature eliminates the complexity of managing login tokens or cookies, enhancing interactions for automation tools and service integrations.

Read more about this and find out how it works by checking out the post, [Introducing simplified interaction with the Airflow REST API in Amazon MWAA](https://aws.amazon.com/blogs/big-data/introducing-simplified-interaction-with-the-airflow-rest-api-in-amazon-mwaa/) [hands on] from Chandan Rupakheti and Hernan Garcia.

**Bottlerocket**

You can now use AMIs for Bottlerocket that are preconfigured to use FIPS 140-3 validated cryptographic modules, including the Amazon Linux 2023 Kernel Crypto API and AWS-LC. Bottlerocket is a Linux-based operating system purpose-built for running containers, with a focus on security, minimal footprint, and safe updates. With these FIPS-enabled Bottlerocket AMIs, the host software uses only FIPS-approved cryptographic algorithms for TLS connections. This includes connectivity to AWS services such as EC2 and Amazon Elastic Container Registry (ECR). Additionally, in regions where FIPS endpoints are available, the AMIs automatically use FIPS-compliant endpoints for these services by default, streamlining secure configurations for containerised workloads.

**Amazon EMR**

Amazon EMR 7.4 is now available, which supports Apache Spark 3.5.2, Apache Hadoop 3.4.0, Trino 446, Apache HBase 2.5.5, Apache Phoenix 5.2.0, Apache Flink 1.19.0, Presto 0.287 and Apache Zookeeper 3.9.2. Amazon EMR 7.4 enables in-transit encryption for 7 additional endpoints used with distributed applications like Apache Livy, Apache Hue, JupyterEnterpriseGateway, Apache Ranger and Apache Zookeeper. This update builds on the previous release Amazon EMR 7.3, which enabled in-transit encryption for 22 endpoints. In-Transit Encryption enables you to run workloads that meet strict regulatory or compliance requirements by protecting the confidentiality and integrity of your data.

**Apache Kafka**

A few weeks ago saw the general availability of Express brokers for Amazon Managed Streaming for Apache Kafka (Amazon MSK). Express brokers are a new broker type for Amazon MSK Provisioned designed to deliver up to 3x more throughput per broker, scale up to 20x faster, and reduce recovery time by 90% as compared to standard Apache Kafka brokers. Express brokers come preconfigured with Kafka best practices by default, support all Kafka APIs, and provide the same low-latency performance that Amazon MSK customers expect, so they can continue using existing client applications without any changes. With Express brokers, customers can provision, scale up, and scale down Kafka cluster capacity in minutes, offload storage management with virtually unlimited pay-as-you-go storage, and build highly resilient applications. Customers can also continue using all of the Amazon MSK key features, including security, connectivity, and observability options, as well as popular integrations, including Amazon MSK Connect, Amazon Simple Storage Service (Amazon S3), AWS Glue Schema Registry, and more. Express brokers are currently available on Kafka version 3.6 and come in three different sizes of Graviton3-based M7g instances: large, 4xlarge, and 16xlarge. Each broker is charged an hourly rate with storage and data ingested charged separately on a pay-as-you-go basis. 

A nice post covers this in more details, so go read it - [Introducing Express brokers for Amazon MSK to deliver high throughput and faster scaling for your Kafka clusters](https://aws.amazon.com/blogs/aws/introducing-express-brokers-for-amazon-msk-to-deliver-high-throughput-and-faster-scaling-for-your-kafka-clusters/)

**Apache Flink**

AWS announced support for a new Apache Flink connector for Amazon DynamoDB. The new connector, contributed by AWS for the Apache Flink open source project, adds Amazon DynamoDB Streams as a new source for Apache Flink. You can now process DynamoDB streams events with Apache Flink, a popular framework and engine for processing and analysing streaming data. Amazon DynamoDB is a serverless, NoSQL database service that enables you to develop modern applications at any scale. DynamoDB Streams provides a time-ordered sequence of item-level changes (insert, update, and delete) in a DynamoDB table. With Amazon Managed Service for Apache Flink, you can transform and analyse DynamoDB streams data in real time using Apache Flink and integrate applications with other AWS services such as Amazon S3, Amazon OpenSearch, Amazon Managed Streaming for Apache Kafka, and more. Apache Flink connectors are software components that move data into and out of an Amazon Managed Service for Apache Flink application. You can use the new connector to read data from a DynamoDB stream starting with Apache Flink version 1.19.

Also worth repeating in case you missed this. Amazon Managed Service for Apache Flink is now billed in one-second increments. There is a ten-minute minimum charge per application. Per-second billing is applicable to applications that are newly launched or already running.

**AWS Amplify**

AWS Amplify Hosting now integrates with Amazon S3 to seamlessly host static website content stored on S3 with just a few clicks. Amplify Hosting is a fully managed service that makes it easy to deploy your websites on a globally available content delivery network (CDN) powered by Amazon CloudFront, allowing secure and performant static website hosting without extensive setup. With AWS Amplify Hosting, you can select the location of your objects within your S3 buckets, deploy your content to a managed CDN, and generate a public HTTPS URL for your website to be accessible anywhere. Amplify Hosting offers CDN hosting for faster performance, simplified custom domain setup, free SSL certificates, redirects, environment management, and monitoring and logging. In addition, Amplify remembers the connection between your S3 bucket and deployed website, so you can easily update your website with a single click when you make changes to website content in your S3 bucket.

Also hot off the press was news that AWS Amplify announced support for Amazon Cognito's new password-less authentication features, enabling developers to implement secure sign-in methods using SMS one-time passwords, email one-time passwords, and WebAuthn passkeys in their applications with Amplify client libraries for JavaScript, Swift, and Android. This update simplifies the implementation of password-less authentication flows, addressing the growing demand for more secure and user-friendly login experiences while reducing the risks associated with traditional password-based systems. This new capability enhances application security and user experience by eliminating the need for traditional passwords, reducing the risk of credential-based attacks while streamlining the login process. Password-less authentication is ideal for organisations aiming to strengthen security and increase user adoption across various sectors, including e-commerce, finance, and healthcare. By removing the frustration of remembering complex passwords, this feature can significantly improve user engagement and simplify account management for both users and organisations.

**Python**

Python 3.13 runtime now available in AWS Lambda, and to find out more read the excellent post from Julian Wood and Leandro Cavalcante Damascena, [Python 3.13 runtime now available in AWS Lambda](https://aws.amazon.com/blogs/compute/python-3-13-runtime-now-available-in-aws-lambda/)

### Videos of the week

**Future-Proof Your Workflow Orchestration: Automate Migration to Airflow**

If you are looking to move your current workflow orchestration solutions to Apache Airflow, check out this video. Impetus' LeapLogic offer a solution that simplifies the migration process, and might be just want you need to get started.

{{< youtube QNtARumrOh8 >}}

**Building with Open Source at AWS & What's Next for Developers**

Check out Adam Seligman and Alex Williams as they talk about open source, and explore some of AWS' current investments in open source.

{{< youtube YduNJIcdRA8 >}}

**Building an open source data strategy on AWS**

Recorded at the AWS Summit London, check out this session for a glimpse on how to take full advantage of open source technologies while leveraging the scalability, flexibility, and cost efficiency of AWS Cloud. The talk looks at data architecture patterns that leverage open source on AWS.

{{< youtube q_TSUsgJf-I >}}


### Events for your diary

If you are planning any events in 2024, either virtual, in person, or hybrid, get in touch as I would love to share details of your event with readers. 

**re:Invent**
**December 2nd - 6th, Las Vegas USA**

AWS's flagship event is only days away. You can [register and watch](https://reinvent.awsevents.com/) some of the event online. In the coming weeks many of the sessions will be uploaded to YouTube, and as usual, we have a dedicated Open Source track which features some really great sessions. 

**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://www.meetup.com/OpenSearch/)

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes: Abhay Saxena, Rashim Gupta, Mershad Irani, Vijay Karumajji, Hernan Garcia, Sriharsh Adari, Chandan Rupakheti, Julian Wood, Leandro Cavalcante Damascena, Amine Hilaly, Christina Andonov, Lukonde Mwila, Wang Rui, Hemanth AVS, Ashok Srirama, Sai Charan Teja Gopaluni, Danny Banks, Dipankar Mazumdar, Matthias Rudolph, Stephen Said, Michael Tran, Alain Krok, Dinesh Sajwan, Sanket Nasre, Ashish Ameta, Seshanth Kannappan, Mahalingam Sivaprakasam, Frank Fan, Sheetal Joshi, Vikram Venkataraman, Ashok Srirama, George John, Leo Li, Prateek Gogia, Mark Terenzoni, Garima Arora, Ravi Kumar Singh, Tarun Chanana, Shawn McCoy, Divya Sharma, Sid Vantair, Naga Appani, Belma Canik, Juhi Patil, Steve Dille, Mark Greenhalgh, Lei Zeng, Ravi Mathur, Jon Haddad, Diego Garcia Garcia, Francisco Morillo, Phaneendra Vuliyaragoli, Dalei Xu, Zhiyong Su, Shijian Tang, Jan Michael Go Tan, JS Labonte, Timur Galeev, Saifeddine Rajhi, Claudio Taverna, and Omid Eidivandi.

**Feedback**

Please please please take 1 minute to [complete this short survey](https://www.pulse.aws/promotion/10NT4XZQ). 

### Stay in touch with open source at AWS

Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) for more open source goodness.

One of the pieces of feedback I received in 2023 was to create a repo where all the projects featured in this newsletter are listed. Where I can hear you all ask? Well as you ask so nicely, you can meander over to[ newsletter-oss-projects](https://github.com/094459/newsletter-oss-projects).

Made with ♥ from DevRel