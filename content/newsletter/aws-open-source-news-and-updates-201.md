---
title: 'AWS open source newsletter #201'
date: '2024-07-10'
tags : [ oss-newsletter, aws open source,  PHP, Apache Airflow, MWAA, Node.js, LLRT, Kubernetes, Amazon EKS, Prometheus, Grafana, eksctl, Valkey, LangChain, Project Lakechain, AWS Amplify, Itsio, Apache Iceberg, Apache Kafka, Apache Cassandra, PyTorch, Apache httpd, Babelfish for Aurora PostgreSQL, Apache Flink, PostgreSQL, MySQL, OpenSearch, OpenZFS, Amazon Linux, FreeRTOS, RabbitMQ, AWS ParallelCluster, Open Container Initiative, Smithy, Cedar, sbt ]
canonicalUrl: "https://community.aws/content/2j5ixvirYqOJ0VjpibXp24LuIZZ/aws-open-source-newsletter-201"
---

##  Edition #201

Welcome to the AWS open source newsletter, issue #201, your trusted source for the very best open source on AWS content. This weeks new projects for you to practice your four freedoms include generative AI infused projects to help you generate your docs, streamline the setting up of your AWS resources, a new experimental framework for building document based workflows, and a cool demo that showcases how you can use generative AI to help translate American Sign Language. We have other projects that provide help functions for observability in your lambda functions, provide demo of how you can move beyond JMX when collecting metrics in your Apache Kafka clusters, as well as a nice Airflow Operator that helps you work with multiple table formats.

Also in this edition we have content covering open source technologies such as Apache Airflow, LLRT, Kubernetes, Prometheus, Grafana, eksctl, Valkey, LangChain, AWS Amplify, Itsio, Apache Iceberg, Apache Kafka, Apache Cassandra, PyTorch, Babelfish for Aurora PostgreSQL, Apache Flink, PostgreSQL, MySQL, OpenSearch, OpenZFS, Amazon Linux, FreeRTOS, RabbitMQ, AWS ParallelCluster, Open Container Initiative, Smithy, and Cedar.

As always, get in touch if you want me to feature your projects in this open source newsletter. Until the next time, I will leave you to dive into the good stuff!

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution. The projects mentioned here do not represent any formal recommendation or endorsement, I am just sharing for greater awareness as I think they look useful and interesting!*

### Tools

**python-bedrock-converse-generate-docs**

[python-bedrock-converse-generate-docs](https://aws-oss.beachgeek.co.uk/409) is a project from AWS Community Builder Alan Blockley that generates documentation for a given source code file using the Anthropic Bedrock Runtime API. The generated documentation is formatted in Markdown and stored in the specified output directory. Alan also put a blog together, [It’s not a chat bot: Writing Documentation](https://aws-oss.beachgeek.co.uk/40a), that shows you how it works and how to get started. The other cool thing about this project is that it is using the [Converse API](https://aws-oss.beachgeek.co.uk/40b) which you should check out if you have not already seen/used it.

**alarm-context-tool**

[alarm-context-tool](https://aws-oss.beachgeek.co.uk/40g) enhances AWS CloudWatch Alarms by providing additional context to aid in troubleshooting and analysis. By leveraging AWS services such as Lambda, CloudWatch, X-Ray, and Amazon Bedrock, this solution aggregates and analyses metrics, logs, and traces to generate meaningful insights. Using generative AI capabilities from Amazon Bedrock, it summarises findings, identifies potential root causes, and offers relevant documentation links to help operators resolve issues more efficiently. The implementation is designed for easy deployment and integration into existing observability pipelines, significantly reducing response times and improving root cause analysis.

**lambda_helpers_metrics**

[lambda_helpers_metrics](https://aws-oss.beachgeek.co.uk/40c) is a metrics helper library for AWS Lambda functions that provides the way to put metrics to the CloudWatch using the Embedded Metric Format ([EMF](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/CloudWatch_Embedded_Metric_Format_Specification.html)). Check out the supporting post, [AWS Lambda Rust EMF metrics helper](https://aws-oss.beachgeek.co.uk/40d).

**cloudysetup**

[cloudysetup](https://aws-oss.beachgeek.co.uk/40e) is a CLI tool designed to streamline AWS resource management using AWS Cloud Control API. It leverages Amazon Bedrock fully managed service with Anthropic - Claude V2 Gen AI model to create, read, update, list, and delete AWS resources by generating configurations compatible with AWS Cloud Control API.

![demo of cloudysetup in action](https://github.com/mostlycloudysky/cloudysetup/blob/master/cloudysetup.gif?raw=true)

**project-lakechain**

[project-lakechain](https://aws-oss.beachgeek.co.uk/401) is an experimental framework based on the AWS Cloud Development Kit (CDK) that makes it easy to express and deploy scalable document processing pipelines on AWS using infrastructure-as-code. It emphasis is on modularity of pipelines, and provides 40+ ready to use components for prototyping complex document pipelines that can scale out of the box to millions of documents. This project has been designed to help AWS customers build and scale different types of document processing pipelines, ranging a wide array of use-cases including metadata extraction, document conversion, NLP analysis, text summarisation, translations, audio transcriptions, computer vision, Retrieval Augmented Generation pipelines, and much more! It is in Alpha stage at the moment, so if you catch any oddities, be sure to flag an issue.

**amazon-mwaa-docker-images**

[amazon-mwaa-docker-images](https://aws-oss.beachgeek.co.uk/3zu) this repo was new to me, so making sure that everyone knows that this repo contains the standard container images used for the Managed Worksflows for Apache Airflow

**apache-xtable-on-aws-samples**

[apache-xtable-on-aws-samples](https://aws-oss.beachgeek.co.uk/3ze) provides sample code to build an Apache Airflow Operator that uses Apache XTable to make a single physical dataset readable in different formats by translating its metadata and avoiding reprocessing of actual data files. The repo will help you build and compile your custom jar file, which you can then use within your Airflow DAG. Check out the supporting blog post from Matthias Rudolph and Stephen Said, [Run Apache XTable on Amazon MWAA to translate open table formats](https://aws-oss.beachgeek.co.uk/3zf).

![metadata translation for open table data formats](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2024/06/26/2_otf_translation_process-1.png)

**csr-builder-for-kms**

[csr-builder-for-kms](https://aws-oss.beachgeek.co.uk/40h) provides a Python library for creating and signing X.509 certificate signing requests (CSRs) with KMS Keys.

### Demos, Samples, Solutions and Workshops

**generative-bi-using-rag**

[generative-bi-using-rag](https://aws-oss.beachgeek.co.uk/40f) is a comprehensive framework designed to enable Generative BI capabilities on customised data sources (RDS/Redshift) hosted on AWS. It offers the following key features:

* Text-to-SQL functionality for querying customised data sources using natural language.
* User-friendly interface for adding, editing, and managing data sources, tables, and column descriptions.
* Performance enhancement through the integration of historical question-answer ranking and entity recognition.
* Customise business information, including entity information, formulas, SQL samples, and analysis ideas for complex business problems. 
* Add agent task splitting function to handle complex attribution analysis problems.
* Intuitive question-answering UI that provides insights into the underlying Text-to-SQL mechanism.
* Simple agent design interface for handling complex queries through a conversational approach.

![architecture for generative bi using rag solution](https://github.com/aws-samples/generative-bi-using-rag/blob/main/assets/aws_architecture.png?raw=true)

**genai-asl-avatar-generator**

[genai-asl-avatar-generator](https://aws-oss.beachgeek.co.uk/405) this repo provides code that demonstrates the power of a number of AWS services working in concert to enable seamless translation from speech/text to American Sign Language (ASL) avatar animations.  Check out the supporting blog post, [Generative AI-powered American Sign Language Avatars](https://aws-oss.beachgeek.co.uk/406), where Suresh Poopandi walks through the project and code and how it all hangs together.

![overview of genai-asl architecture](https://github.com/aws-samples/genai-asl-avatar-generator/blob/main/images/GenASL-referencearchitecture.jpg?raw=true)

**kafka-client-metrics-to-cloudwatch-with-kip-714**

[kafka-client-metrics-to-cloudwatch-with-kip-714](https://aws-oss.beachgeek.co.uk/407) provides reference code from my colleague Ricardo Ferreria, that shows how to push metrics from your Apache Kafka clients to Amazon CloudWatch using the KIP-714: Client Metrics and Observability. To use this feature, you must use a Kafka cluster with the version 3.7.0 or higher. It also requires the Kraft mode enabled, which is the new mode to run Kafka brokers without requiring Zookeeper. Check out his supporting blog post, [KIP-714: Keep your Kafka Clusters Close, and your Kafka Clients Closer](https://aws-oss.beachgeek.co.uk/408)

### AWS and Community blog posts

**This weeks essential reading**

These were my favourite reads since the last newsletter was published. Let me know what you think.

* [Announcing the end-of-support for PHP runtimes 8.0.x and below in the AWS SDK for PHP](https://aws-oss.beachgeek.co.uk/3zi) make sure you check out this important post if you are a PHP developer or user
* [Announcing the end of support for Node.js 16.x in the AWS SDK for JavaScript (v3)](https://aws-oss.beachgeek.co.uk/3zm) is essential reading for folks using the AWS SDK for Javascript and Node.js 16
* [Amazon MWAA best practices for managing Python dependencies](https://aws-oss.beachgeek.co.uk/3zl) describes best practices for managing your requirements file in your Amazon MWAA environment, essential reading for any Apache Airflow developers out there

**The best from around the Community**

Each week I spent a lot of time reading posts from across the AWS community on open source topics. In this section I share what personally caught my eye and interest, and  I hope that many of you will also find them interesting. 

This week, AWS Hero Elliot Cordo starts this roundup with one of my favourite open source projects, Apache Airflow. In [Federated Airflow with SQS](https://aws-oss.beachgeek.co.uk/3zv) Elliot demonstrates how you can leverage Amazon SQS to enable a data mesh inspired infrastructure that allows you to potentially cover a number of different use cases. As always, bear in mind that the use of this approach will occupy one of your worker slots, so this in combination with deferrable operators (which are supported by the Amazon Provider package) might be the route to go down. From Apache Airflow to Low Latency Runtime (LLRT), a project featured in [#188](https://blog.beachgeek.co.uk/newsletter/aws-open-source-news-and-updates-188/) that provides a lightweight JavaScript runtime. AWS Community Builder Matteo Depascale has provided a very nice overview and tutorial on how to get started with this project in, [Building Lightning-Fast AWS Lambda Functions with LLRT and Terraform](https://aws-oss.beachgeek.co.uk/3zw). 

Next up are a couple of cloud native related posts. First up is AWS Community Builder Romar Cablao who is continuing on his "back to basics" series of posts with his latest, [Back2Basics: Monitoring Workloads on Amazon EKS](https://aws-oss.beachgeek.co.uk/3zx). In this latest post you will see how to use Prometheus and Grafana to  monitor some basic workloads. Following that we have AWS Community Builder Ant Weiss who has put together [9 Ways to Spin Up an EKS Cluster - Way 3 - eksctl](https://aws-oss.beachgeek.co.uk/3zy), which as described, dives into the ways of eksctl. Fear it no more after reading this post.

No round up is complete these days without some generative AI goodness, and we have some cracking posts. Starting off with my colleague Abhisek Gupta who provides a hands on guide on how to integrate Valkey with LangChain (in Go) with his short post, [Maintain chat history in generative AI apps with Valkey](https://aws-oss.beachgeek.co.uk/3zz). Following that we have João Galego with [Build Document Processing Pipelines with Project Lakechain](https://aws-oss.beachgeek.co.uk/400), where he shows you how to create cloud-native, AI-powered document processing pipelines on AWS with Project Lakechain. If you have not heard about Project Lakechain, it is a cool, new project from AWS Labs for creating modern, AI-powered, document processing pipelines (see projects above for a link to the repo). In [Use AWS Generative AI CDK constructs to speed up app development](https://aws-oss.beachgeek.co.uk/402) Abhishek is back with more generative AI goodness, this time showing you how you can assemble and deploy the infrastructure for a RAG solution using AWS CDK for Python, specifically the AWS Generative AI Constructs Library. The final post in this round up is from Laith Al-Saadoon, who shows you how to leverage the new native tool-calling capabilities in the LangChain AWS package, using Anthropic Claude 3 models with Amazon Bedrock, in the post [Build generative AI agents with LangChain and Anthropic Claude 3 models on Amazon Bedrock](https://aws-oss.beachgeek.co.uk/403)

To close things for this round up we have  AWS Hero Yasunori Kirimoto who provides a nice primer and introduction into AWS Amplify Gen2 Hosting in his post, [Trying Various Settings for AWS Amplify Gen2 Hosting](https://aws-oss.beachgeek.co.uk/404). If you are looking for a good introduction, why not try this.

**Cloud Native**

* [Simplify Service Mesh Deployment with Solo.io’s AWS Marketplace add-on for Amazon EKS](https://aws-oss.beachgeek.co.uk/3zs) explores one of the options you have when looking to manage microservices workloads on AWS using Istio
* [Scale and simplify ML workload monitoring on Amazon EKS with AWS Neuron Monitor container](https://aws-oss.beachgeek.co.uk/3zt) looks at the recent launch of the AWS Neuron Monitor container, that simplifies the integration of advanced monitoring tools such as Prometheus and Grafana, enabling you to set up and manage your machine learning (ML) workflows with AWS AI Chips [hands on]

![cloudwatch container insights dashboard on grafana](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2024/06/20/neuronekslp001.png)

**Other posts to check out**

* [Accelerate query performance with Apache Iceberg statistics on the AWS Glue Data Catalog](https://aws-oss.beachgeek.co.uk/3zh) demonstrates how column-level statistics for Iceberg tables work with Redshift Spectrum, going on to showcase the performance benefit of the Iceberg column statistics with the TPC-DS dataset [hands on]
* [Configure a custom domain name for your Amazon MSK cluster](https://aws-oss.beachgeek.co.uk/3zq) explains how you can use an NLB, Route 53, and the advertised listener configuration option in Amazon MSK to support custom domain names with MSK clusters when using SASL/SCRAM authentication [hands on]

![example dns records for custom domain for apache kafka](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2024/06/11/bdb4099_image007-1024x375.png)

* [How PayU uses Amazon Keyspaces (for Apache Cassandra) as a feature store](https://aws-oss.beachgeek.co.uk/3zr) is a case study from one of India's leading digital finance service providers, that shows how they use Amazon Keyspaces (for Apache Cassandra) as the feature store for real-time, low-latency inference in the payment flow [hands on]
* [Accelerated PyTorch inference with torch.compile on AWS Graviton processors](https://aws-oss.beachgeek.co.uk/3zj) shows you how to optimise torch.compile performance on AWS Graviton3-based EC2 instances, and then how to use the optimisations to improve inference performance [hands on]
* [Use Amazon CloudWatch Contributor Insights for general analysis of Apache logs](https://aws-oss.beachgeek.co.uk/3zk) provides a hands on guide on how to monitor and perform analysis of Apache logs using CloudWatch Contributor Insights [hands on]

![example metrics for apache web server in cloudwatch](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2024/06/18/13.png)

* [Workaround for T-SQL global temporary tables in Babelfish for Aurora PostgreSQL](https://aws-oss.beachgeek.co.uk/3zn) covers how to implement T-SQL global temporary table behavior in Babelfish for Aurora PostgreSQL using permanent table [hands on]
* [Build a real-time streaming generative AI application using Amazon Bedrock, Amazon Managed Service for Apache Flink, and Amazon Kinesis Data Streams](https://aws-oss.beachgeek.co.uk/3zo) explores how to incorporate generative AI capabilities in your streaming architecture using Amazon Bedrock and Managed Service for Apache Flink using asynchronous requests - very cool [hands on]

![overview of architecture for real time streaming generative AI with apache flink and amazon bedrock](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2024/06/06/BDB-4051-image001.png)

* [Uncover social media insights in real time using Amazon Managed Service for Apache Flink and Amazon Bedrock](https://aws-oss.beachgeek.co.uk/3zp) shows you how to combine real-time analytics with the capabilities of generative AI and use state-of-the-art natural language processing (NLP) models to analyze tweets through queries related to your brand, product, or topic of choice [hands on]

![overview of solution architecture](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2024/06/17/social-4.png)

### Quick updates

**Valkey**

Valkey General Language Independent Driver for the Enterprise (GLIDE), an open source Valkey client library, is now available. Valkey is an open source key-value data store that supports a variety of workloads such as caching, and message queues. Valkey GLIDE is one of the official client libraries for Valkey and it supports all Valkey commands. GLIDE supports Valkey 7.2 and above, and Redis open source 6.2, 7.0, and 7.2. Application programmers can use GLIDE to safely and reliably connect their applications to services that are Valkey- and Redis OSS-compatible.

Valkey GLIDE is designed for reliability, optimised performance, and high-availability, for Valkey- and Redis OSS- based applications. It is supported by AWS, and is preconfigured with best practices learned from over a decade of operating Redis OSS-compatible services used by thousands of customers. To help ensure consistency in application development and operations, GLIDE is implemented using a core driver framework, written in Rust, with language specific extensions. This design ensures consistency in features across languages, and reduces overall complexity. In this release, GLIDE is available for Java and Python, with support for additional languages actively under development.

You can read more in [Introducing Valkey GLIDE, an open source client library for Valkey and Redis open source](https://aws-oss.beachgeek.co.uk/3zd), where Asaf Porat Stoler and Mickey Hoter discuss the benefits of Valkey GLIDE.

![overview of valkey glide client architecture](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2024/07/09/DBBLOG-4254-img1.png)

**Apache Airflow**

You can now create Apache Airflow version 2.9 environments on Amazon Managed Workflows for Apache Airflow (MWAA). Apache Airflow 2.9 is the latest minor release of the popular open-source tool that helps customers author, schedule, and monitor workflows. Amazon MWAA is a managed orchestration service for Apache Airflow that makes it easier to set up and operate end-to-end data pipelines in the cloud. Apache Airflow 2.9 introduces several notable enhancements, such as new API endpoints for improved dataset management, custom names in dynamic task mapping for better readability, and advanced scheduling options including conditional expressions for dataset dependencies and the combination of dataset and time-based schedules.

Check out the launch post [Introducing Amazon MWAA support for Apache Airflow version 2.9.2](https://aws-oss.beachgeek.co.uk/3za), where Hernan Garcia and Parnab Basak walk you through some of these new features and capabilities, how you can use them, and how you can set up or upgrade your Amazon MWAA environments to Airflow 2.9.2.

**Apache Flink**

We have a few updates for you, starting off with news that Amazon Managed Service for Apache Flink now supports Apache Flink 1.19. This version includes new capabilities in the SQL API such as state TTL configuration and session window support. Flink 1.19 also includes Python 3.11 support, trace reporters for job restarts and checkpointing, and more. You can use in-place version upgrades for Apache Flink to adopt the Apache Flink 1.19 runtime for a simple and faster upgrade to your existing application. Francisco Morillo and Lorenzo Nicora has put together [Amazon Managed Service for Apache Flink now supports Apache Flink version 1.19](https://aws-oss.beachgeek.co.uk/3zc), so you can dive deeper into this update.

Amazon Managed Service for Apache Flink also introduced the ListApplicationOperations and DescribeApplicationOperation APIs for visibility into operations that were performed on your application. These APIs provide details about when an operation was initiated, its current status, success or failure, if your operation triggered a rollback, and more so that you can take follow-up action.

Finally, Amazon Managed Service for Apache Flink introduced the system-rollback feature to automatically revert your application to the previous running application version during Flink job submission if there are code or configuration errors. You can now opt-in to this feature for improved application uptime. You may encounter errors such as insufficient permissions, incompatible savepoints, and other errors when you perform application updates, Flink version upgrades, or scaling actions. System-rollback identifies these errors during job submission and prevents a bad update to your application. This gives you higher confidence in rolling out changes to your application faster.

**PostgreSQL**

A couple of updates for you.

Amazon RDS for PostgreSQL now supports new PL/Rust crates such as serde and serde_json crates, allowing you to exchange information between server and client or between servers by serialising and deserialising data structures in your PL/Rust user-defined functions. The release also includes support for regex crate that allow you to search strings for matches of a regular expression and url crate that implements the URL standard to provide parsing and deparsing of URL strings. With support for additional crates, you can now build more types of extensions on RDS for PostgreSQL using Trusted Language Extensions for PostgreSQL (pg_tle). pg_tle is an open source development kit to help you build extensions written in a trusted language, such as PL/Rust, that run safely on PostgreSQL. Support for serde, serde_json, regex, and url crates is available on database instances in Amazon RDS running PostgreSQL 16.3-R2 and higher, 15.7-R2 and higher, 14.12-R2 and higher, and 13.15-R2 and higher in all applicable AWS Regions. 

Amazon RDS for PostgreSQL 17 Beta 2 is now available in the Amazon RDS Database Preview Environment, allowing you to evaluate the pre-release of PostgreSQL 17 on Amazon RDS for PostgreSQL. You can deploy PostgreSQL 17 Beta 2 in the Amazon RDS Database Preview Environment that has the benefits of a fully managed database. PostgreSQL 17 includes updates to vacuuming that reduces memory usage, improves time to finish vacuuming, and shows progress of vacuuming indexes. With PostgreSQL 17, you no longer need to drop logical replication slots when performing a major version upgrade. PostgreSQL 17 continues to build on the SQL/JSON standard, adding support for `JSON_TABLE` features that can convert JSON to a standard PostgreSQL table. The `MERGE` command now supports the `RETURNING` clause, letting you further work with modified rows. PostgreSQL 17 also includes general improvements to query performance and adds more flexibility to partition management with the ability to SPLIT/MERGE partitions. 

**MySQL**

Two important updates for you.

Amazon Relational Database Service (RDS) for MySQL announced Amazon RDS Extended Support minor version 5.7.44-RDS.20240529. We recommend that you upgrade to this version to fix known security vulnerabilities and bugs in prior versions of MySQL. Learn more about the bug fixes and patches in this version in the Amazon RDS User Guide. Amazon RDS Extended Support provides you more time, up to three years, to upgrade to a new major version to help you meet your business requirements. During Extended Support, Amazon RDS will provide critical security and bug fixes for your MySQL on Aurora and RDS after the community ends support for a major version. You can run your MySQL databases on Amazon RDS with Extended Support for up to three years beyond a major version’s end of standard support date.

Amazon Relational Database Service (Amazon RDS) for MySQL now also supports MySQL minor version 8.0.37. We recommend that you upgrade to the latest minor versions to fix known security vulnerabilities in prior versions of MySQL, and to benefit from the bug fixes, performance improvements, and new functionality added by the MySQL community. Learn more about the enhancements in RDS for MySQL 8.0.37 in the Amazon RDS user guide.

**OpenSearch**

A couple of great updates for OpenSearch users.

Amazon OpenSearch Service has added support for AI powered Natural Language Query Generation in OpenSearch Dashboards Log Explorer. With Natural Language Query Generation, you can accelerate analysis by asking log exploration questions in plain English, which are then automatically translated to the relevant Piped Processing Language (PPL) queries and executed to fetch the requested data. With this new natural language support, you can get started quickly with log analysis without first having to be proficient in PPL. Further, it opens up log analysis to a wider set of team members who can simply explore their log data by asking questions like - “show me the count of 5xx errors for each of the pages on my website” or “show me the throughput by hosts”. This also helps advanced users in constructing complex queries by allowing for iterative refinement of both the natural language questions and the generated PPL. This feature is available at no cost for customers running managed clusters with OpenSearch 2.13 or above.

Amazon OpenSearch Ingestion now allows you to seamlessly ingest streaming data from Confluent Cloud Kafka clusters into your Amazon OpenSearch Service managed clusters or Serverless collections without the need for any third-party data connectors. With this integration, you can now use Amazon OpenSearch Ingestion to perform near-real-time aggregations, sampling and anomaly detection on data ingested from Confluent Cloud, helping you to build efficient data pipelines to power your complex observability use cases. mazon OpenSearch Ingestion pipelines can consume data from one or more topics in a Confluent Kafka cluster and transform the data before writing it to Amazon OpenSearch Service or Amazon S3. While reading data from Confluent Kafka clusters via Amazon OpenSearch Ingestion, you can configure the number of consumers per topic and tune different fetch parameters for high and low priority data. You can also optionally use Confluent Schema Registry to specify your data schema to dynamically read data at ingest time. You can also check out this blog post by Confluent to learn more about this feature.

**OpenZFS**

Amazon FSx for OpenZFS now supports highly available (HA) Single-AZ deployments, offering high availability and consistent sub-millisecond latencies for use cases like data analytics, machine learning, and semiconductor chip design that can benefit from high availability but do not require multi-zone resiliency. Single-AZ HA file systems provide a lower-latency and lower-cost storage option than Multi-AZ file systems for these use cases, while offering all the same data management capabilities and features. Before today, FSx for OpenZFS offered Single-AZ non-HA file systems, which provide sub-millisecond read and write latencies, and Multi-AZ file systems, which provide high availability and durability by replicating data synchronously across AZs. With Single-AZ HA file systems, customers can now achieve both high availability and consistent sub-millisecond latencies at a lower cost relative to Multi-AZ file systems for workloads such as data analytics, machine learning, and semiconductor chip design that do not need multi-zone resiliency because they're operating on a secondary copy of the data or data that can be regenerated. Check out which AWS Regions you can do this [here](https://aws-oss.beachgeek.co.uk/3zb)

**Amazon Linux**

Today are announcing the availability of the latest quarterly update to AL2023 containing the latest version of PHP and .NET, along with IPA Client and mod-php. Customers can take advantage of newer versions of PHP and .NET to ensure their applications are secure and efficient. Additionally, AL2023.5 includes packages like mod-php and IPA client that can improve web server performance and simplify identity management integration, respectively, further streamlining development workflows and enhancing overall system efficiency.

**FreeRTOS**

AWS announced the third release of FreeRTOS Long Term Support (LTS) - FreeRTOS 202406 LTS. FreeRTOS LTS releases provide feature stability with security updates and critical bug fixes for two years. The new LTS release includes the latest FreeRTOS kernel v11.1 that supports Symmetric Multiprocessing (SMP) and Memory Protection Units (MPU) and recently updated libraries, such as the FreeRTOS-Plus-TCP v4.2.1 library and the Over-the-Air (OTA) library, providing you with an improved IPv6 and OTA capabilities. With the FreeRTOS LTS releases, you can continue to maintain your existing FreeRTOS code base and avoid any potential disruptions resulting from FreeRTOS version upgrades. Similar to the previous FreeRTOS LTS release, FreeRTOS 202406 LTS includes libraries that have been validated for memory safety with the C Bounded Model Checker (CBMC) and have undergone specific code quality checks, including MISRA-C compliance and Coverity static analysis to help improve code safety, portability, and reliability in embedded systems. For more information, refer to the LTS Code Quality Checklist. The support period for the previous LTS release will end on Nov-2024, thus providing you with an overlapping time window to migrate your projects to the new LTS release.

**RabbitMQ**

Amazon MQ now provides support for RabbitMQ version 3.13, which includes several fixes and performance improvements to the previous versions of RabbitMQ supported by Amazon MQ. Starting from RabbitMQ 3.13, Amazon MQ will manage patch version upgrades for your brokers. All brokers on version 3.13 will be automatically upgraded to the latest compatible and secure patch version in your scheduled maintenance window. If you are running earlier versions of RabbitMQ, such as 3.8, 3.9, 3.10, 3.11 or 3.12, we strongly encourage you to upgrade to RabbitMQ 3.13. This can be accomplished with just a few clicks in the AWS Management Console. Amazon MQ for RabbitMQ will soon end support for RabbitMQ versions 3.8, 3.9 and 3.10.

**AWS ParallelCluster**

AWS ParallelCluster is a fully-supported and maintained open-source cluster management tool that enables R&D customers and their IT administrators to operate high-performance computing (HPC) clusters on AWS. AWS ParallelCluster is designed to automatically and securely provision cloud resources into elastically-scaling HPC clusters capable of running scientific, engineering, and machine-learning (ML/AI) workloads at scale on AWS.

AWS ParallelCluster 3.10 is now generally available. Key features of this release include support for Amazon Linux 2023 and Terraform. With Terrafrom support, customers can automate deployment and management of clusters similar to how they use Terraform to automate other parts of their AWS infrastructure. Other important features in this release include support for connecting clusters to an external Slurm database daemon (Slurmdbd) to follow best practices of enabling Slurm accounting in a multi-cluster environment, and a new allocation strategy configuration to allocate EC2 Spot instances from the lowest-priced, highest-capacity availability pools to minimize job interruptions and save costs. For more details on the release, review the AWS ParallelCluster 3.10.0 [release notes](https://github.com/aws/aws-parallelcluster/releases/tag/v3.10.0).

**Open Container Initiative**

Amazon Elastic Container Registry (ECR) now supports Open Container Initiative (OCI) Image and Distribution specification version 1.1, which includes support for Reference Types, simplifying the storage, discovery, and retrieval of artefacts related to a container image. AWS Container Services customers can now easily store, discover, and retrieve artefacts such as image signatures and Software bill of materials (SBOMs) as defined by OCI 1.1 for a variety of supply chain security use cases such as image signing and vulnerability auditing. Through ECR’s support of Reference types, customers now have a simple user experience for distributing and managing artefacts related to these use cases, consistent with how they manage container images today.

OCI Reference Types support in ECR allows customers to distribute artefacts in their repositories alongside their respective images. Artefacts for a specific image are discovered through their reference relationship, and can be pulled the same way images are pulled. In addition, ECR’s replication feature supports referrers, copying artefacts to destination regions and accounts so they are ready to use alongside replicated images. ECR Lifecycle Policies also supports referring artefacts by deleting references when a subject image is deleted as a result of a lifecycle policy rule expire action, making management of referring artefacts simple with no additional configuration.

**Kubernetes**

Amazon Elastic Kubernetes Service (EKS) now provides the flexibility to create Kubernetes clusters without the default networking add-ons, enabling you to easily install open source or third party alternative add-ons or self-manage default networking add-ons using any Kubernetes lifecycle management tool. Every EKS cluster automatically comes with default networking add-ons including Amazon VPC CNI, CoreDNS, and kube-proxy providing critical functionality that enables pod and service operations for EKS clusters. EKS also allows you to bring open source or third party add-ons and tools that manage their lifecycle. With today’s launch, you can skip the installation of default networking add-ons when creating the cluster, making it easier to install alternative add-ons. This also simplifies self-managing default networking add-ons using any lifecycle management tool like Helm or Kustomize, without needing to first remove the Kubernetes manifests of the add-ons from the cluster. You can opt out of default networking add-ons during cluster creation from the EKS console, CLI, API, and IaC tools like AWS CloudFormation. 


### Videos of the week

**Generating Kotlin SDKs with Smithy**

As software becomes increasingly distributed and the number of APIs available for consumption grows, the challenge of maintaining synchronisation among numerous clients and servers becomes progressively cumbersome. How do clients and servers agree on the API used to communicate with one another? How can the API evolve such that existing clients continue to work without redeploying? How do teams ensure a consistent experience across APIs?

Smithy is an interface definition language (IDL) and set of tools that empowers developers to build clients and servers in multiple languages. It is used to define the APIs for AWS services and generate the AWS SDKs, including the AWS SDK for Kotlin. In this video, that was recorded from KotlinConf, Ian Botsford and Aaron Todd show how the Kotlin code generator for Smithy works, what features it provides, and how to leverage it to build Kotlin (multiplatform) SDKs for your own services. No prerequisite knowledge of Smithy required.

{{< youtube Wsra04prG-E >}}


**Cedar**

A couple of videos that cover two areas of Cedar: Entity Attributes and Enriching Cedar Policies.

Cedar policies allow us to precisely describe the application state relevant for authorisation decisions. This is great because it enables users to accurately reflect their authorisation intent! But, as with any expressive language, there is always the possibility to make mistakes. This video shows how to introduce a layer of indirection between principals and resources with user groups and point out a couple places where a typo might lead to policies that don't mean what they think they should. You will see how you can use Cedar policy validation to help ensure you get things right.

{{< youtube eBUerHynfYU >}}


In this second video, you will learn how Entity attributes make it easy to write much higher-level policies.

{{< youtube UYj5SBOiUCk >}}


**Accelerate SaaS Development with SaaS Builder Toolkit for AWS**

Featured in newsletter [#198](https://community.aws/content/2h6H82ceGfVpqbr5NOAWnvS1oO5/aws-open-source-newsletter-198), SaaS Builder Toolkit for AWS (SBT) is an open-source developer toolkit to implement SaaS best practices and increase developer velocity. It offers a high-level object-oriented abstraction to define SaaS resources on AWS imperatively using the power of modern programming languages. Using SBT’s library of infrastructure constructs, you can easily encapsulate SaaS best practices in your SaaS application, and share it without worrying about boilerplate logic. SBT is built on top of the AWS Cloud Development Kit (CDK). It offers a number of higher-order constructs (L2, L2.5 and L3) to short-circuit the time required to build SaaS applications. Specifically, SBT attempts to codify several control plane and application plane concepts into reusable components, promoting reuse and reducing boilerplate code. Pranjit Biswas walks you through this project, to help you get a deeper understanding and show you how to get started.

{{< youtube slo2vPPtldo >}}

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

So thank you to the following open source heroes: Elliot Cordo, Laith Al-Saadoon, João Galego, Abhisek Gupta, Romar Cablao, Ant Weiss, Matteo Depascale, Sotaro Hikita, Kalaiselvi Kamaraj, Kyle Duong, Sandeep Adwankar, Noritaka Sekiyama, Sean O'Brien, Sunita Nadampalli, Vivek Kumar, Matthew Barker, Sukhchander Khanna, Shaileen Savage, Mike Ellis,  Trivikram Kamat, Vanshika Nigam, Amit Arora, Felix John, Michelle Mei-Li Pfister, Francisco Morillo, Subham Rakshit, Sergio Garcés Vitale, Subham Rakshit, Mark Taylor, Hemant Singh, Mohit Bansal, Akshaya Rawat, Hemant Singh, Mohit Bansal, Art Tuazon, Petr McAllister, Niithiyn Vijeaswaran, Emir Ayar, Geeta Gharpure, Ziwen Ning, Albert Opher, Rohit Talluri, and Yasunori Kirimoto.

**Feedback**

Please please please take 1 minute to [complete this short survey](https://www.pulse.aws/promotion/10NT4XZQ). 

### Stay in touch with open source at AWS

Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) for more open source goodness.

One of the pieces of feedback I received in 2023 was to create a repo where all the projects featured in this newsletter are listed. Where I can hear you all ask? Well as you ask so nicely, you can meander over to[ newsletter-oss-projects](https://aws-oss.beachgeek.co.uk/3l8).

Made with ♥ from DevRel
