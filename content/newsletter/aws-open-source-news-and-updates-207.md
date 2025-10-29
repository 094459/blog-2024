---
title: 'AWS open source newsletter #207'
date: '2025-02-28'
tags : [ oss-newsletter, aws open source, kro, AWS CDK, OpenTelemetry, Kubernetes, Amazon EKS, dstack, GraphRAG, FFMpeg, ArgoCD, Terragrunt, OpenTofu, Django, PostgreSQL, Apache Kafka, Amazon Linux, Apache Flink, Apache Airflow, MWAA, Apache Spark, MySQL, Qonto, Prometheus, Amazon EMR, Apache Iceberg, OpenSearch, Valkey, AWS Amplify, Lustre, InfluxDB, Cedar, Aider ]
canonicalUrl: "https://dev.to/aws/aws-open-source-newsletter-207-1c55"
---

##  Edition #207 - February 2025

Welcome to issue #207 of the AWS open source newsletter, the newsletter where we try and provide you the best open source on AWS content. As always, we have more great new projects to check out, which include real time analysis of your client calls to AWS APIs, a dashboard for all your AWS Health Events, an EBS analysis tool, a SIEM tool that allows you to query your AWS events, a really cool AI Coding Assistant powered by Amazon Bedrock, a really great demo of how to implement an MCP server, running WhispherX on AWS Lambda, and more!

The projects will keep you busy until next month for sure, but we also have plenty of reading material in this months newsletter. We feature projects including kro, AWS CDK, OpenTelemetry, Kubernetes, dstack, GraphRAG, FFMpeg, ArgoCD, Terragrunt, OpenTofu, Django, PostgreSQL, Apache Kafka, Amazon Linux, Apache Flink, Apache Airflow, Apache Spark, MySQL, Qonto, Prometheus, Amazon EMR, Apache Iceberg, OpenSearch, Valkey, AWS Amplify, Lustre, InfluxDB, Cedar, and Aider. Finally, don't forget to check out the videos as I have a couple of great ones for you in this edition.

As always, get in touch if you want me to feature your projects in this open source newsletter. Until the next time, I will leave you to dive into the good stuff!

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution. The projects mentioned here do not represent any formal recommendation or endorsement, I am just sharing for greater awareness as I think they look useful and interesting!*

### Tools

**aws-client-monitor**

[aws-client-monitor](https://github.com/tsypuk/aws-client-monitor) is a new tool from Roman Tsypuk designed to analyse applications interacting with AWS services. It's particularly useful during local development, troubleshooting, or profiling third-party applications. It allows you to do real-time monitoring, capturing and displaying AWS API invocations in real time, and is easy to get started with. It comes with a gorgeous dashboard, so this is on my todo list to try out. Very nice Roman!

![example dashboard for aws-client-monitor](https://github.com/tsypuk/aws-client-monitor/blob/main/ui.png?raw=true)

**aws-health-events-insight**

[aws-health-events-insight](https://github.com/aws-samples/aws-health-events-insight) this project provides a very nice solution to centralise, store and then analyse your AWS Health events. Health Events Intelligence Dashboards and Insights (HEIDI) Data Collection Framework enables you to collect data from different accounts, regions and organisations. Check out the README for more details  including how to deploy and configure this solution in your AWS environment.

![demo of aws health event insight dashboard](https://github.com/aws-samples/aws-health-events-insight/blob/main/img/dashboard.gif?raw=true)

**ebsight**
                                                                 
[ebsight](https://github.com/sjramblings/ebsight) is a Python-based analysis tool developed by Stephen Jones in response to AWS's new EBS snapshot size reporting feature. This tool leverages the newly introduced FullSnapshotSizeInBytes field to provide comprehensive insights into EBS volume usage, performance metrics, and cost optimisation opportunities. After you have checked the repo out and gone through the README, why not read the supporting blog post, [Unleash the Power of EBSight for Optimal AWS Storage Management](https://sjramblings.io/unleash-the-power-of-ebsight-for-optimal-aws-storage-management)

**tailpipe**

[tailpipe](https://github.com/turbot/tailpipe) is an open source SIEM for instant log insights from our friends at Turbot, powered by DuckDB. It allows you to analyse millions of events in seconds, right from your terminal. Check out the README that includes more info include a nice video demo of this in works. Bob Tordella (who we have featured many times over the years in this newsletter), has put together a blog post too, which is a must read. Go check it out - [Query AWS CloudTrail Logs Locally with SQL](https://dev.to/aws-builders/query-aws-cloudtrail-logs-locally-with-sql-4jcj)

As the project says, select * from logs

**vscode-iam-service-principal-snippets**

[vscode-iam-service-principal-snippets](https://github.com/dannysteenman/vscode-iam-service-principal-snippets) is the latest VSCode plugin from AWS Community Builder Danny Steenman ([his fifth](https://www.linkedin.com/posts/dannysteenman_today-marks-a-small-but-significant-milestone-activity-7292070581011660800-iwbT/)). This VS Code extension provides autocompletion of all AWS services that can be used as Service Principals in your IAM policies. Very hand indeed! Danny wrote:

> The reason I created it is because when I write IAM policies or roles, I constantly found myself breaking out of my flow to hunt down the right AWS Service Principal from a GitHub gist maintained by the community.
> It was effective, but having to toggle over to a browser, search, locate the specific principal, then switch back to VS Code was frustrating and inefficient. 
> Therefore I built this extension to keep me fully in the VS Code environment with context-aware auto-completion. Now, not only am I saving time, but the autocompletion suggestions are also automatically updated every week as new principals are released. 

I've installed it, what are you waiting for...

**bedrock-engineer**

[bedrock-engineer](https://github.com/aws-samples/bedrock-engineer) looks like an amazing project and one I am trying to find some time to play with. bedrock-engineer is Autonomous software development agent apps using Amazon Bedrock, capable of customise to create/edit files, execute commands, search the web, use knowledge base, use multi-agents, generative images and more. The project README has a short video that goes over some of the functionality and its pretty neat. 

![functionality of bedrock-engineer](https://github.com/aws-samples/bedrock-engineer/blob/main/assets/agent-chat-diagram.png?raw=true)

**StsSamlDriver**

[StsSamlDriver](https://github.com/awslabs/StsSamlDriver) is A Python-based SAML authentication handler for AWS STS that allows you to get temporary credentials using SAML to the AWS CLI, or an application written using an AWS SDK without the need to screen scrape or emulate a browser.

Many tools exist today to get AWS credentials into an environment that can work with the AWS CLI or AWS SDK using SAML. However most of these scripts rely on parsing HTML or fully emulating a browser to do so which is difficult and may not be supported by various IDPs, especially on identity-as-a-service providers who may update the HTML on their login flows without notice.

This tool avoids interacting directly with a SAML IDP in any capacity by starting up a server on http://localhost:8090, which will receive a SAML assertion from your IDP on /saml from your browser. After receiving the assertion, the code will attempt to call AssumeRoleWithSAML to assume the role, and deliver the temporary credentials to your application and optionally launch an AWS console session. The server only listens for a single SAML assertion and will stop running after one is received.

You can use this tool by updating the ACS server of your SAML IDP (or target, or whatever your IDP's name is for where the SAML assertion is sent to) for a given application targeted at assuming a role on AWS to http://localhost:8090/saml , or doing similar with a userscript service like tampermoney, or custom browser plugins to override a SAML destination.

### Demos, Samples, Solutions and Workshops

**MCP2Lambda**

[MCP2Lambda](https://github.com/danilop/MCP2Lambda) is a project from my good friend Danilo Poccia and is a really great example of how Model Control Protocol (MCP) provides Large Language Model (LLM) with additional capabilities and flexibility. In this demo sample, an MCP server acts as a bridge between MCP clients and AWS Lambda functions, allowing generative AI models to access and run Lambda functions as tools. This is useful, for example, to access private resources such as internal applications and databases without the need to provide public network access. This approach allows the model to use other AWS services, private networks, and the public internet. I love that! As always, Danilos repos and code is top notch, so git this a go and don't forget to star it if you like it.

**whisperx-on-aws-lambda**

[whisperx-on-aws-lambda](https://github.com/vincentclaes/whisperx-on-aws-lambda) is a project from Vincent Claes that shows you how you can run [WhisperX](https://github.com/m-bain/whisperX) (one of the most versatile and feature-rich Whisper variation that provides fast automatic speech recognition) on AWS Lambda - WhisperX goes serverless!

**auth-pep-pdp**

[auth-pep-pdp](https://github.com/JimmyDqv/serverless-handbook/tree/main/Solutions/auth-pep-pdp) is another solution from AWS Hero Jimmy Dahlqvist to add to the already great selection he shares in his repo. It provides code to help you implement PDP (Policy Decision Point) and a PEP (Policy Enforcement Point). We will build an simple API and use Amazon API Gateway and Lambda Authorizer as the PEP. It gets extra credit as its using Cedar for the policies.  To help you get started with this project, you can check out the excellent README as well as the supporting blog post, [PEP and PDP for Secure Authorization with AVP ](https://dev.to/aws-heroes/pep-and-pdp-for-secure-authorization-with-avp-290c).

![overview of architecture](https://github.com/JimmyDqv/serverless-handbook/blob/main/Solutions/auth-pep-pdp/images/overview-avp.png?raw=true)

**draw-an-app**

[draw-an-app](https://github.com/aws-samples/draw-an-app) is a neat demo application that uses AWS Bedrock's Claude 3 Sonnet model to convert hand-drawn UI sketches into working web applications. It supports two modes of operation: 1/ Real-time webcam capture for immediate sketching and conversion, or 2/ Image upload through a user-friendly Streamlit interface. I have not tried this one yet, but if you do, let me know how you get on.

### AWS and Community blog posts

**This weeks essential reading**

Here are the posts that I think are essential reads, so start here.

* [Kube Resource Orchestrator, From Experiment to Community Project](https://aws.amazon.com/blogs/opensource/kube-resource-orchestrator-from-experiment-to-community-project/) - looks at a project that we launched at KubeCon in 2024, kro (a new experimental way to simplify and empower the use of custom APIs and resources with Kubernetes) and how the likes of Microsoft Azure, Google Cloud, and AWS are collaborating together

* [Announcing CDK Garbage Collection](https://aws.amazon.com/blogs/devops/announcing-cdk-garbage-collection/) -  is essential reading for folks (like me) who use AWS CDK and need help in managing those unused CDK Assets in your AWS account - tools like CDK Garbage Collection play a crucial role in maintaining clean, efficient, and cost-effective cloud environments [hands on]

![decision flow of assets under gc](https://d2908q01vomqb2.cloudfront.net/7719a1c782a1ba91c031a682a0a2f8658209adbf/2025/02/21/Screenshot-2025-02-13-at-1.38.54-PM.png)

* [Announcing the general availability of AWS .NET OpenTelemetry libraries](https://aws.amazon.com/blogs/dotnet/announcing-the-general-availability-of-aws-net-opentelemetry-libraries/) - in case you missed this announcement, the OpenTelemtry dotnet packages have been reworked for simplicity and to conform to the latest OpenTelemetry naming conventions, and include new features like support for enhanced observability in AWS SDK for .NET and additional instrumentation for AWS services

* [A deep dive into Amazon EKS Hybrid Nodes](https://aws.amazon.com/blogs/containers/a-deep-dive-into-amazon-eks-hybrid-nodes/) - dives deep into this new capability that was launched at re:Invent, that simplifies how you can deploy your workloads with Kubernetes on-premises or at the edge on Amazon EKS [hands on]

![hybrid architecture with eks hybrid nodes](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2025/01/27/Picture1-4.jpg)

* [Introducing the GraphRAG Toolkit](https://aws.amazon.com/blogs/database/introducing-the-graphrag-toolkit/) - describe how you can get started with the [GraphRAG Toolkit](https://github.com/awslabs/graphrag-toolkit) (featured in #206 of the newsletter), a Python toolkit for building GraphRAG applications [hands on]

* [Efficient distributed training with AWS EFA](https://dstack.ai/blog/distributed-training-with-aws-efa/) - it is always great to hear from the open source community, and Andrey Cheptsov got in touch about this project, dstack, that provides a lightweight, open-source alternative to Kubernetes & Slurm, simplifying AI container orchestration with multi-cloud & on-prem support that also natively supports NVIDIA, AMD, TPU, and Intel accelerators - read the post to find out how this project leverages Amazon Elastic Fabric Adapter (EFA) to supercharge distributed training tasks [hands on]

**Community round up**

Each week I spent a lot of time reading posts from across the AWS community on open source topics. In this section I share what personally caught my eye and interest, and I hope that many of you will also find them interesting.

This weeks sees an old friend in the way of FFMpeg. It has been a long time since I have used FFMpeg in anger, but I was reminded about the happy times by Malte Reimann who posted [How to install FFmpeg on Amazon Linux](https://community.aws/content/2rLsGgmLh36ajFAxX1p2esS8zPP/how-to-install-ffmpeg-on-amazon-linux), which does exactly what it says.

AWS Community Builder Jonas Neumann is all about caring and sharing, specifically sharing tips he has learned from using AWS CDK in his post, [AWS CDK tips and tricks for developers](https://dev.to/aws-builders/aws-cdk-tips-and-tricks-for-developers-2ogo) - some good stuff in here. AWS Community Builder Alejandro Velez continues with the infrastructure as code theme in his post, [GitOps and IaC at Scale – AWS, ArgoCD, Terragrunt, and OpenTofu – Part 1](https://dev.to/aws-builders/gitops-and-iac-at-scale-aws-argocd-terragrunt-and-opentofu-part-1-2ie9) where he kicks off the first in a series of posts diving deep into GitOps. The final post in this mini IaC roundup is from AWS Hero Rehan van der Merwe who has put together [CDK Constructs for connecting AWS Lambda to Tailscale](https://rehanvdm.com/blog/cdk-lambda-tailscale-extension-and-proxy) where he explains how to connect AWS Lambda functions to a Tailscale network. Check out his other blog posts too if you get the time, they are all excellent.

I have been spending a lot of time exploring AI Coding Assistants like Amazon Q Developer to see how they can help open source developers, and Ricardo Tasso came up with a great example in how he is using Q Developer to generate deployment configurations for Kubernetes. He has written this up in his post, [Creating Deployment Configurations for EKS with Amazon Q](https://community.aws/content/2tEtIXupTg9cQkRNKnVHGik2U0J/creating-deployment-configurations-for-eks-with-amazon-q) so go check it out (you can get started with Amazon Q Developer for free by registering your [Builder ID here](https://s12d.com/builder-id)). 
[Langfuse](https://github.com/langfuse/langfuse) is an open source LLM engineering platform that helps teams collaboratively develop, monitor, evaluate, and debug AI applications. AWS Community Builder Matsuda shows you how you can deploy this, using CDK to make it simple. If this sounds like something you are interested in, go read the post [Self-Hosting Langfuse v3 on AWS Using CDK](https://dev.to/aws-builders/self-hosting-langfuse-v3-on-aws-using-cdk-508a).

If you are a Django developer and are keen to get started with Amazon Aurora DSQL then AWS Community Builder Kevin Kiruri has you covered in his post, [AWS Aurora DSQL for Django Developers: A Step-by-Step Guide](https://dev.to/aws-builders/aws-aurora-dsql-for-django-developers-a-step-by-step-guide-4pah). Nice!

If you were ever wondering what the performance characteristics of Apache Kafka producers (clients) was between languages, then I have something you might be interesting in reading. AWS Community Builder Mohammed has put together [Rust vs Node — Kafka producer performance with AWS Lambda](https://dev.to/aws-builders/rust-vs-node-kafka-producer-performance-with-aws-lambda-26mk) that dives into this topic. No spoilers, you will have to read the post to find out.

**Cloud Native**

* [Automating AL2023 custom hardened AMI updates for Amazon EKS managed nodes](https://aws.amazon.com/blogs/containers/automating-al2023-custom-hardened-ami-updates-for-amazon-eks-managed-nodes/) - walks you through building an automated pipeline to build, deploy and validate Amazon EKS custom AMIs, using the CIS Amazon Linux 2023 Benchmark Level 2 AMI and EC2 Image Builder to create custom AMI [hands on]

![pipeline overview](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2025/02/11/Solution-Architecture.png)

* [Announcing ASCP integration with Pod Identity: Enhanced security for secrets management in Amazon EKS](https://aws.amazon.com/blogs/security/announcing-ascp-integration-with-pod-identity-enhanced-security-for-secrets-management-in-amazon-eks/) - cover use-case scenarios for single and cross-account secrets using Pod Identity integration with AWS Secrets and Configuration Provider (ASCP), which now integrates with Pod Identity which is the new standard for AWS Identity and Access Management (IAM) integration with Amazon EKS [hands on]

![solution overview](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2025/02/10/img1-1.png)

* [Organizational best practices for implementing EKS Anywhere at scale](https://aws.amazon.com/blogs/containers/organizational-best-practices-for-implementing-eks-anywhere-at-scale/) - looks at best practices for your EKS Anywhere deployments, and provides a lot of details that will help make sure you set yourself up for success

**Data and Analytics**

* [Handle errors in Apache Flink applications on AWS](https://aws.amazon.com/blogs/big-data/error-handling-in-apache-flink-applications/) - discusses the strategies for handling errors in Apache Flink applications, although you can apply the general principles discussed here to stream processing applications at large [hands on]
* [Building and operating data pipelines at scale using CI/CD, Amazon MWAA and Apache Spark on Amazon EMR by Wipro](https://aws.amazon.com/blogs/big-data/building-and-operating-data-pipelines-at-scale-using-ci-cd-amazon-mwaa-and-apache-spark-on-amazon-emr-by-wipro/) - looks at some frameworks that have been developed by Wipro that address common issues and pain points associated with traditional ETL tools

![overview of solution architecture](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2024/12/13/BDB-3581-Building-and-operating-image001-1.png)

* [Perform minor/major version upgrades for Amazon Aurora MySQL Global Database with minimum downtime](https://aws.amazon.com/blogs/database/perform-minor-major-version-upgrades-for-amazon-aurora-mysql-global-database-with-minimum-downtime/) - shows how you can use the blue/green deployment technique to perform engine version upgrades for Aurora MySQL global database clusters with minimal downtime [hands on]

![fall back and fall forward diagram](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2025/02/18/DBBLOG-3257-6-RollBackApproaches.png)

* [Self-managed multi-tenant vector search with Amazon Aurora PostgreSQL](https://aws.amazon.com/blogs/database/self-managed-multi-tenant-vector-search-with-amazon-aurora-postgresql/) - is a multi part post that explores the process of building a multi-tenant generative AI application using Aurora PostgreSQL-Compatible for vector storage [hands on]
* [Monitor the health of Amazon Aurora PostgreSQL instances in large-scale deployments](https://aws.amazon.com/blogs/database/monitor-the-health-of-amazon-aurora-postgresql-instances-in-large-scale-deployments/) - provides a solution to help you achieve better visibility into the health of your Aurora PostgreSQL instances [hands on]
* [Simplify database authentication management with the Amazon Aurora PostgreSQL pg_ad_mapping extension](https://aws.amazon.com/blogs/database/simplify-database-authentication-management-with-the-amazon-aurora-postgresql-pg_ad_mapping-extension/) -  looks into how you can use Kerberos authentication for Amazon Aurora PostgreSQL-Compatible Edition using AWS Directory Service for Microsoft Active Directory, and particularly the new pg_ad_mapping extension and how it can help you manage access control more efficiently [hands on]
* [Introducing Qonto’s Prometheus RDS Exporter – An Open Source Solution to Enhance Monitoring Amazon RDS](https://aws.amazon.com/blogs/opensource/introducing-qontos-prometheus-rds-exporter-an-open-source-solution-to-enhance-monitoring-amazon-rds/) - shares how AWS customer Qonto created the [Prometheus RDS Exporter](https://github.com/qonto/prometheus-rds-exporter) for Amazon RDS monitoring and why they decided to share it with the open source community under an MIT license [hands on]

* [Hybrid big data analytics with Amazon EMR on AWS Outposts](https://aws.amazon.com/blogs/big-data/hybrid-big-data-analytics-with-amazon-emr-on-aws-outposts/) - demonstrates how to use Amazon EMR on Outposts as a managed big data processing service in your on-premises setup [hands on]

![hybrid architecture with amazon emr on outposts](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2025/02/04/image-71.png)

* [Enhance your workload resilience with new Amazon EMR instance fleet features](https://aws.amazon.com/blogs/big-data/enhance-your-workload-resilience-with-new-amazon-emr-instance-fleet-features/) - walks you through the latest enhancements to Amazon EMR instance fleets that mark a significant advancement in big data processing, addressing key challenges in resource allocation, scalability, and reliability
* [Migrate from Standard brokers to Express brokers in Amazon MSK using Amazon MSK Replicator](https://aws.amazon.com/blogs/big-data/migrate-from-standard-brokers-to-express-brokers-in-amazon-msk-using-amazon-msk-replicator/) - essential reading if you are looking to migrating from a Standard broker MSK cluster to an Express broker MSK cluster, showing how using MSK Replicator provides a seamless, efficient transition with minimal downtime [hands on]
* [Access data in Amazon S3 Tables using PyIceberg through the AWS Glue Iceberg REST endpoint](https://aws.amazon.com/blogs/storage/access-data-in-amazon-s3-tables-using-pyiceberg-through-the-aws-glue-iceberg-rest-endpoint/) - demonstrates how to access Iceberg tables stored in S3 Tables using [PyIceberg](https://github.com/apache/iceberg-python), a Python library for programmatic access to Iceberg table metadata as well as to table data in Iceberg format [hands on]
* [OpenSearch Vector Engine is now disk-optimized for low cost, accurate vector search](https://aws.amazon.com/blogs/big-data/opensearch-vector-engine-is-now-disk-optimized-for-low-cost-accurate-vector-search/) - provides you with details on why you might want to run the OpenSearch Vector Engine on disk mode, and provides you tips on getting started [hands on]
* [Monitor server-side latency for Amazon ElastiCache for Valkey](https://aws.amazon.com/blogs/database/monitor-server-side-latency-for-amazon-elasticache-for-valkey/) - is exactly what you expect, walks you through new CloudWatch metrics that help you measure latency for your ElastiCache for Valkey instances, looking at a few scenarios where these latency metrics could help in troubleshooting latency spikes in your ElastiCache cluster [hands on]

![overview of Valkey metrics for measuring latency](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2025/01/17/DBBLOG-4596-img1-v3-1.png)

**Other posts to check out**

* [Build a Scalable Search Solution with AWS Amplify and OpenSearch Serverless](https://aws.amazon.com/blogs/mobile/build-a-scalable-search-solution-with-aws-amplify-and-opensearch-serverless/) - goes into how to create a movie search solution using AWS Amplify and Amazon OpenSearch [hands on]

* [Port .NET Framework workloads to Linux with Amazon Q Developer, Part 1: Class libraries](https://aws.amazon.com/blogs/dotnet/port-net-framework-workloads-to-linux-with-amazon-q-developer-part-1-class-libraries/) - this first in a series of posts that helps you explore how you can use AI Coding Assistants to help you modernise your workloads, in this case, porting a class library [hands on]
* [Unlock higher performance for file system workloads with scalable metadata performance on Amazon FSx for Lustre](https://aws.amazon.com/blogs/storage/unlock-higher-performance-for-file-system-workloads-with-scalable-metadata-performance-on-amazon-fsx-for-lustre/) - provides a great deep dive in how you can scale metadata performance on Amazon FSx for Lustre to allow you to consolidate workloads on a single file system [hands on]
* [Optimizing Amazon FSx for Lustre storage consumption using automatic data tiering with Amazon S3](https://aws.amazon.com/blogs/storage/optimizing-fsx-for-lustre-storage-consumption-using-automatic-data-tiering-with-amazon-s3/) - demonstrates how you can tier data between FSx for Lustre and Amazon S3 by implementing an automated file release mechanism [hands on]

![architecture overview of implementing a high performance layer in front of Amazon S3](https://d2908q01vomqb2.cloudfront.net/e1822db470e60d090affd0956d743cb0e7cdf113/2025/02/12/Figure-1-Architecture-Diagram-for-the-FSx-for-Lustre-Amazon-S3-automated-file-release.jpg)

### Quick updates

**PostgreSQL**

Over the past month we have had a few updates with regards to versions that Amazon Relational Database Service (RDS) for PostgreSQL now supports.

The latest minor versions 17.4, 16.8, 15.12, 14.17, and 13.20. Please note, this release supports the versions released by the PostgreSQL community on February, 20,2025 to address the regression that was part of the February 13, 2025 release. Also announced was support for 17.3, 16.7, 15.11, 14.16, and 13.19. The release also includes updates for PostgreSQL extensions such as pg_active 2.1.4, pg_cron 1.6.5, pg_partman 5.2.4, and others.
 
We recommend that you upgrade to the latest minor versions to fix known security vulnerabilities in prior versions of PostgreSQL, and to benefit from the bug fixes added by the PostgreSQL community. You can use automatic minor version upgrades to automatically upgrade your databases to more recent minor versions during scheduled maintenance windows. You can also use Amazon RDS Blue/Green deployments for RDS for PostgreSQL using physical replication for your minor version upgrades.

If you are using Amazon CloudWatch Database Insights, it now provides lock contention diagnostics for Aurora PostgreSQL instances. This feature helps you identify the root cause behind both ongoing and historical lock contention issues within minutes. The lock contention diagnostics feature is available exclusively in the Advanced mode of CloudWatch Database Insights. With this launch, you can visualise a locking condition in the Database Insights console, which shows the relationship between blocking and waiting sessions. The visualisation helps you quickly identify the dominating sessions, queries, or objects causing lock contention. Additionally, this feature persists historical locking data for 15 months, allowing you to analyse and investigate historical locking conditions. You no longer need to manually run custom queries or rely on application logs to diagnose lock contention issues, streamlining the troubleshooting process.

**MySQL**

Amazon Relational Database Service (Amazon RDS) for MySQL now supports MySQL minor versions 8.0.41 and 8.4.4. We recommend that you upgrade to the latest minor versions to fix known security vulnerabilities in prior versions of MySQL, and to benefit from the bug fixes, performance improvements, and new functionality added by the MySQL community. You can leverage automatic minor version upgrades to automatically upgrade your databases to more recent minor versions during scheduled maintenance windows. You can also leverage Amazon RDS Managed Blue/Green deployments for safer, simpler, and faster updates to your MySQL instances.

Amazon RDS for MySQL also announced Amazon RDS Extended Support for minor version 5.7.44-RDS.20250103. We recommend that you upgrade to this version to fix known security vulnerabilities and bugs in prior versions of MySQL. Learn more about the bug fixes and patches in this version in the Amazon RDS User Guide. Amazon RDS Extended Support provides you more time, up to three years, to upgrade to a new major version to help you meet your business requirements. During Extended Support, Amazon RDS will provide critical security and bug fixes for your RDS for MySQL databases after the community ends support for a major version. You can run your MySQL databases on Amazon RDS with Extended Support for up to three years beyond a major version’s end of standard support date.

**Apache Kafka**

Amazon Managed Streaming for Apache Kafka (Amazon MSK) now supports Apache Kafka version 3.8. You can now create new clusters using version 3.8 with either KRAFT or ZooKeeper mode for metadata management or upgrade your existing ZooKeeper based clusters to use version 3.8. Apache Kafka version 3.8 includes several bug fixes and new features that improve performance. Key new features include support for compression level configuration. This allows you to further optimize your performance when using compression types such as lz4, zstd and gzip, by allowing you to change the default compression level. For more details and a complete list of improvements and bug fixes, see the Apache Kafka [release notes for version 3.8](https://downloads.apache.org/kafka/3.8.0/RELEASE_NOTES.html).

**InfluxDb**

If you are using Amazon Timestream for InfluxDB then we recently announced the launch of storage scaling functions for Amazon Timestream for InfluxDB, allowing you to scale your allocated storage and change your storage Tiers as needed. With Storage Scaling, in you few simple steps you have greater flexibility and control over your time-series data processing and analysis.

Timestream for InfluxDB is used in applications that require high-performance time-series data processing and analysis. You can quickly respond to changes in data ingestion rates, query volumes, or other workload fluctuations by moving to a faster more performant storage tier or extending your allocated storage capacity, ensuring that your Timestream for InfluxDB instances always have the necessary resources to handle your workload and cost effectively. This means you can focus on building and deploying your applications, rather than worrying about storage sizing and management.

**Lustre**

Amazon FSx for Lustre, a service that provides high-performance, cost-effective, and scalable file storage for compute workloads, now enables you to upgrade the Lustre version of your FSx for Lustre file systems. This feature allows you to benefit from the enhancements available in newer Lustre versions on your existing file systems. FSx for Lustre provides fully-managed file systems built on Lustre, the world's most popular open-source high performance file system. FSx for Lustre supports multiple long-term support Lustre versions released by the Lustre community. Newer Lustre versions provide benefits such as performance enhancements, new features, and support for the latest Linux kernel versions for your client instances.

**Cedar**

Amazon Verified Permissions is a permissions management and fine-grained authorisation service for the applications that you build. Using Cedar, an expressive and analysable open-source policy language, developers and admins can define policy-based access controls using roles and attributes for more granular, context-aware access control. For example, an HR application might call Amazon Verified Permissions (AVP) to determine if Alice is permitted to access Bob’s performance evaluation, given that she is in the HR Managers group. Customers can use Cedar JSON format to pass entity data describing the principal (Alice) and the resource (Bob’s performance evaluation).

Amazon Verified Permissions now supports the same JSON format for entity and context data, as the Cedar SDK. Developers can use this simpler format for authorisation requests. This aligns the Amazon Verified Permissions API more closely with the open source Cedar SDK, and simplifies moving from the SDK to Amazon Verified Permissions or vice versa.

**Kubernetes**

A few important updates this month.

AWS CodePipeline introduced a new action to deploy to Amazon Elastic Kubernetes Service (Amazon EKS). This action enables you to easily deploy your container applications to your EKS clusters, including those in private VPCs. Previously, if you wanted to deploy to a EKS cluster within a private network, you had to initialise and maintain a compute environment within the private network. Now, you can simply provide the name of the EKS cluster and add this action to your pipeline. The pipeline will automatically establish a connection into your private network to deploy your container application, without additional infrastructure needed. This streamlined approach reduces your operational overhead and simplifies your deployment process.

Kubernetes version 1.32 introduced several new features and bug fixes, and AWS is excited to announce that you can now use Amazon Elastic Kubernetes Service (EKS) and Amazon EKS Distro to run Kubernetes version 1.32. Starting today, you can create new EKS clusters using version 1.32 and upgrade existing clusters to version 1.32 using the EKS console, the eksctl command line interface, or through an infrastructure-as-code tool. Kubernetes version 1.32 introduces several improvements including stable support for custom resource field selectors and auto removal of persistent volume claims created by stateful sets. This release removes v1beta3 API version of FlowSchema and PriorityLevelConfiguration. To learn more about the changes in Kubernetes version 1.32, see our documentation and the Kubernetes [project release notes.](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG/CHANGELOG-1.32.md)

AWS Secrets Manager also announced that AWS Secrets and Configuration Provider (ASCP) now integrates with Amazon Elastic Kubernetes Service (Amazon EKS) Pod Identity. This integration simplifies IAM authentication for Amazon EKS when retrieving secrets from AWS Secrets Manager or parameters from AWS Systems Manager Parameter Store. With this new capability, you can manage IAM permissions for Kubernetes applications more efficiently and securely, enabling granular access control through role session tags on secrets. ASCP is a plugin for the industry-standard Kubernetes Secrets Store CSI Driver. It enables applications running in Kubernetes pods to retrieve secrets from AWS Secrets Manager easily, without the need for custom code or restarting containers when secrets are rotated. The AWS EKS Pod Identity, streamlines the process of configuring IAM permissions for Kubernetes applications in a more efficient and secure way. This integration combines the strengths of both components, enhancing secret management in Amazon EKS environments. Previously, ASCP relied on IAM Roles for Service Accounts (IRSA) for authentication. Now, you can choose between IRSA and Pod Identity for IAM authentication using the new optional parameter "usePodIdentity". This flexibility allows you to adopt the authentication method that best suits your security requirements and operational needs.

**AWS Elastic Beanstalk**

AWS Elastic Beanstalk is a service that provides the ability to deploy and manage applications in AWS without worrying about the infrastructure that runs those applications. There were a couple of updates that will be of interest to open source folk.

First up is news that AWS Elastic Beanstalk now enables customers to build and deploy Python 3.13 applications on Amazon Linux 2023 (AL2023) platform. This latest platform support allows developers to leverage the newest features and improvements in Python while taking advantage of the enhanced security and performance of AL2023. Python 3.13 on AL2023 delivers enhanced interactive interpreter capabilities, improved error messages, and important security and API improvements. Developers can create Elastic Beanstalk environments running Python 3.13 on AL2023 through the Elastic Beanstalk Console, CLI, or API.

Following that is news that AWS Elastic Beanstalk now enables customers to build and deploy PHP 8.4 applications on Amazon Linux 2023 (AL2023) platform. This latest platform support allows developers to take advantage of the newest PHP features while leveraging the enhanced security and performance of AL2023. Developers can create Elastic Beanstalk environments running PHP 8.4 on AL2023 through the Elastic Beanstalk Console, CLI, or API.

### Videos of the week

**Deploy DeepSeek-R1 Models on Kubernetes with Amazon EKS**

Those Containers from the Couch folks are back to mischief, this time looking at how you you can deploy DeepSeek-R1 on Kubernetes. In this video, Sai is joined by AWS Solutions Architects Lucas and Tiago to talk about why DeepSeek is different and show you a demo of deploying it on Amazon EKS Auto Mode. We use Amazon EKS Auto Mode for flexibility and scalability on the underlying compute, removing the need for you to manage infrastructure tasks.

{{< youtube -YeNNOZ0y84 >}}

**Build Software with Amazon Bedrock AI and Aider Open Source**

[Aider](https://github.com/Aider-AI/aider) is a super nice open source generative AI pair programming tool that I have been using on/off for a while. It provides a great tool for those of us who prefer text and command line environments. In this video, AWS Ambassador Trevor Sullivan from StratusGrid, takes you through the setup process of a containerized development environment with Aider, using Amazon Bedrock to provide access to Large Language Models (LLM) 

{{< youtube CTzX1qB_S1k >}}

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes: Roman Tsypuk, Stephen Jones, Bob Tordella, Danny Steenman, Danilo Poccia, Vincent Claes, Jimmy Dahlqvist, Andrey Cheptsov, Senaka Ariyasinghe, Deependra Shekhawat, Ranjini Menon, Rajesh Matkar, Wanchen Zhao, Wassim Benhallam, Qaisar Dar, Vikrant Telka, Tom McDonald, Kaizen Conroy, Adam Keller, Josh Hart, Nihilson Gnanadason, Deepmala Agarwal, Kashif Khan, Mandisa Nxumalo, Ravi Kumar Singh, Gaurav Sharma, Abhishek Nanda, Jayaprakash Alawala, Rajesh Singh, Rodrigo Bersa, Akshay Aggarwal, Stephanie Shen, Subham Rakshit, Srividya Parthasarathy, Dylan Qu, Kalyan Kumar Neelampudi, Aritra Gupta, Krishna Sarabu, Priyanka Sadhu, Pavankumar Kasani, Ty Augustine, Alexis Tekin, Jeremy Ber, Jagadeesh Chitikesi, Philip Pittle, Ulili Nhaga, Vivien de Saint Pern, Camille Hoarau, Damien Cupif, Vincent Mercier, Anil Maktala, Chris Splinter, Elamaran Shanmugam, Re Alvarez Parmar, Dylan Tong, Vamshi Vijay Nakkirtha, Yasha Jayaprakash, Mihir Mangalvedhekar, Rajbir Singh,  Ian Robinson, Abdellah Ghassel, Jesse Butler, Shoukat Ghouse, Fernando Galves, Anand Komandooru, Anubhava Srivastava, Noorul Hasan, Li Liu, Subhash Dike, Mohammed, Kevin Kiruri, Matsuda, Rehan van der Merwe, Jonas Neumann, Malte Reimann, and Alejandro Velez.

**Feedback**

Please please please take 1 minute to [complete this short survey](https://www.pulse.aws/promotion/10NT4XZQ). 

### Stay in touch with open source at AWS

Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) for more open source goodness.

One of the pieces of feedback I received in 2023 was to create a repo where all the projects featured in this newsletter are listed. Where I can hear you all ask? Well as you ask so nicely, you can meander over to[ newsletter-oss-projects](https://github.com/094459/newsletter-oss-projects).

Made with ♥ from DevRel

