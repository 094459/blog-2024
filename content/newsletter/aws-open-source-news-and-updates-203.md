---
title: 'AWS open source newsletter #203'
date: '2024-08-27'
tags : [ oss-newsletter, aws open source,  Langfuse, Steampipe, Ray, Apache Spark, AWS Amplify, Flutter, Valkey, O3DE, AWS CDK, LangChain, Kubernetes, Amazon EKS, Argo Workflows, OpenTofu, Bottlerocket, Karpenter, OpenTelemetry, Apache Flink, Apache Pinot, Apache Kafka, openCypher, Apache Iceberg, Apache Airflow, MWAA, MySQL, PostgreSQL, Deequ, OCSF, GraphStorm, OpenShift, Amazon EMR, ActiveMQ, Red Hat Enterprise Linux, Cedar ]
canonicalUrl: "https://community.aws/content/2lEQqY1XJZZxCGRztsxlG8vXbQc/aws-open-source-newsletter-203"
---

Welcome to the AWS open source newsletter, the newsletter where we try and provide you the best open source on AWS content. As always, more great new projects are featured in this edition, #203. Projects to check out include: how you can proxy OpenAI requests through Amazon Bedrock, security tools that help you stay one step ahead of bad actors, a way of implementing CDK Pipelines in a less opinionated way, a tool that helps you validate your AWS IAM policies, a toolkit to help get you started with good practices when creating CloudFormation templates, some demo code that demonstrate how you can implement zero downtime updates to your applications, as well as some really cool demos and use cases of generative AI in action (too many to mention, so check them all out!).

Once you have had time to take a look at the projects, there is still lots to check out. In this edition we feature content covering some of your favourite open source projects, including Cedar, Langfuse, Steampipe, Ray, Apache Spark, AWS Amplify, Flutter, Valkey, O3DE, AWS CDK, LangChain, Kubernetes, Argo Workflows, OpenTofu, Bottlerocket, Karpenter, OpenTelemetry, Apache Flink, Apache Pinot, Apache Kafka, openCypher, Apache Iceberg, Apache Airflow, MySQL, PostgreSQL, Deequ, OCSF, GraphStorm, OpenShift, Amazon EMR, ActiveMQ, and Red Hat Enterprise Linux.

As always, get in touch if you want me to feature your projects in this open source newsletter. Until the next time, I will leave you to dive into the good stuff!

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution. The projects mentioned here do not represent any formal recommendation or endorsement, I am just sharing for greater awareness as I think they look useful and interesting!*

### Tools

**bedrock-litellm**

[bedrock-litellm](https://github.com/aws-samples/bedrock-litellm) is an awesome project that provides a way of proxying requests in the OpenAI format, so that they will work with Amazon Bedrock. OpenAI is often one of the default options for integrating various generative AI tools and libraries, and now you have a way of being able to point those to use foundational models managed by Amazon Bedrock. It uses [litellm](https://www.litellm.ai/) to do this, and is deployed in a Kubernetes cluster.

**aws-config-rule-rds-logging-enabled-remediation**

[aws-config-rule-rds-logging-enabled-remediation](https://github.com/aws-samples/aws-config-rule-rds-logging-enabled-remediation) provides code that will help you checks if respective logs of Amazon Relational Database Service (Amazon RDS) are enabled using AWS Config rule 'rds-logging-enabled'. The rule is NON_COMPLIANT if any log types are not enabled. AWS Systems Manager Automation document used as remediation action to enable the logs export to CloudWatch for the RDS instances that are marked NON_COMPLIANT.

**apeman**

[apeman](https://github.com/hotnops/apeman) is a new tool that helps security people to map and visualise AWS identity attack paths. The README provides detailed instructions on how to get up and running, but I also found the blog post, [ Project Apeman : A Comprehensive Guide To Graph-Based AWS Security Analysis](https://kalilinuxtutorials.com/project-apeman/) very helpful. Daniel Heinsen talks more about this in depth in his talk at SpecterOps.

{{< youtube Gs5BZplrxe4 >}}

**aws-mine**

[aws-mine](https://github.com/StevenSmiley/aws-mine) is a project from Steven Smiley that should interest security folk. It provides a [honey](https://uk.norton.com/blog/iot/what-is-a-honeypot) token system for AWS, that allows you to create AWS access keys that can be placed in various places to tempt bad guys. If used, you will be notified within ~4 minutes. You can then investigate that asset to determine if it may have been compromised. 

![demo of aws-mine running](https://github.com/StevenSmiley/aws-mine/blob/main/demo.gif?raw=true)

**bedrock-embed-web**

[bedrock-embed-web](https://github.com/tagazok/bedrock-embed-web) is a new project from my colleague Olivier Leplus that makes it easier than ever to embed Amazon Bedrock foundation models within a chat interface in your web applications.

![demo of bedrock-embed-web](https://github.com/tagazok/bedrock-embed-web/blob/main/public/demo-containerId.png?raw=true)

**cdk-express-pipeline**

[cdk-express-pipeline](https://github.com/rehanvdm/cdk-express-pipeline) is the latest project from AWS Hero Rehan van der Merwe (who's project I use to track usage metrics of this newsletter!) which provides an alternative to those of you who want to use some of the features of AWS CDK Pipelines, but perhaps need it less opinionated. CDK Express Pipelines is a library built on the AWS CDK, allowing you to define pipelines in a CDK-native method. It leverages the CDK CLI to compute and deploy the correct dependency graph between Waves, Stages, and Stacks using the .addDependency method, making it build-system agnostic and an alternative to AWS CDK Pipelines. Check out the clear documentation which will help you get started in no time.

**improve-employee-productivity-using-genai**

[improve-employee-productivity-using-genai](https://github.com/aws-samples/improve-employee-productivity-using-genai) is an innovative code sample designed to elevate the efficiency and effectiveness of writing tasks through the integration of AI technologies. Tailored for AWS users, this assistant example utilises Amazon Bedrock and generative AI models to automate the creation of initial templates, that can also be customised for your own needs. Users can input both text and images, benefiting from the multimodal capabilities of cutting-edge AI like the Claude 3 family, which supports dynamic interaction with multiple data types. The README is very comprehensive and covers not only how to set up and configure this project, but also has lots of great short videos of it in action. Looks really cool, and a project for my weekend I think.

![overview of solution architecture](https://github.com/aws-samples/improve-employee-productivity-using-genai/blob/main/backend/artifacts/architecture-diagram.png?raw=true)

**validate-aws-policies**

[validate-aws-policies](https://github.com/velez94/validate-aws-policies) is a Python command line tool from  Alejandro Velez to validate aws policies using boto3 and Access Analyzer API. You can check out his supporting blog post (including demo video) [Continuous Delivery applied to Authorization with IAM Identity Center and AWS IAM Access Analyzer – Part 1](https://dev.to/aws-builders/continuous-deployment-applied-to-authorization-with-iam-identity-center-and-aws-iam-access-analyzer-part-1-7h6) that shows you how you can incorporate this tool as part of your CI/CD pipeline.

![demo of validate-aws-policies cli at work](https://github.com/velez94/validate-aws-policies/blob/main/docs/img/rec_validate.gif?raw=true)

**aws-cloudformation-starterkit**

[aws-cloudformation-starterkit](https://github.com/dannysteenman/aws-cloudformation-starterkit) is a new project from AWS Community Builder Danny Steenman that should accelerate AWS infrastructure deployment for CloudFormation users. It's designed for both beginners and seasoned pros, featuring quick CI/CD setup, multi-environment support, and automated security checks. Very nice repo, clear and detailed documentation, so make sure you check this project out.

### Demos, Samples, Solutions and Workshops

**build-an-agentic-llm-assistant**

[build-an-agentic-llm-assistant](https://github.com/aws-samples/build-an-agentic-llm-assistant) this repo provides code that you can follow along as part of the "Build an agentic LLM assistant on AWS" workshop. This hands-on workshop, aimed at developers and solution builders, trains you on how to build a real-life serverless LLM application using foundation models (FMs) through Amazon Bedrock and advanced design patterns such as: Reason and Act (ReAct) Agent, text-to-SQL, and Retrieval Augemented Generation (RAG). It complements the Amazon Bedrock Workshop by helping you transition from practicing standalone design patterns in notebooks to building an end-to-end llm serverless application. Check out the README for additional links to the workshop text, as well as more details on how this repo works.

![overview of agentic llm assistant workshop architecture](https://github.com/aws-samples/build-an-agentic-llm-assistant/blob/main/assets/agentic-assistant-workshop-architecture.png?raw=true)

**deploy-langfuse-on-ecs-with-fargate**

[deploy-langfuse-on-ecs-with-fargate](https://github.com/aws-samples/deploy-langfuse-on-ecs-with-fargate) This repository contains the AWS CDK Python code for deploying the Langfuse application using Amazon Elastic Container Registry (ECR) and Amazon Elastic Container Service (ECS). If you are not familiar with Langfuse, it is is an open-source LLM engineering platform that helps teams collaboratively debug, analyze, and iterate on their LLM applications.

![screenshot of langfuse running on ecs](https://raw.githubusercontent.com/aws-samples/deploy-langfuse-on-ecs-with-fargate/main/assets/06-trace-detail.png)

**webapp-form-builder**

[webapp-form-builder ](https://github.com/aws-samples/webapp-form-builder) - this repo was built to accelerate the development of web forms on the frontend using the AWS Cloudscape Design System. Cloudscape is an open source design system to create web applications. It was built for and is used by Amazon Web Services (AWS) products and services. This solution provides you with a sample application that utilises components of the Cloudscape Design System that are commonly used in web-forms where users are required to input data.  Check out the more expansive README for more details of how this works and how to get started.

![cloudscape example form](https://github.com/aws-samples/webapp-form-builder/blob/main/example-form.png?raw=true)

**sample-code-for-a-secure-vault-using-aws-nitro-enclaves**

[sample-code-for-a-secure-vault-using-aws-nitro-enclaves](https://github.com/aws-samples/sample-code-for-a-secure-vault-using-aws-nitro-enclaves) - This repository contains a sample secure vault solution built using AWS Nitro Enclaves, a feature available exclusively through the AWS Nitro System hypervisor on supported Amazon EC2 instances. A vault solution is useful when you need to ensure sensitive data (such as Protected Health Information (PHI)/Personally Identifiable Information (PII)) is properly secured at rest and can only be decrypted through approved channels. Check out more details about how cool Nitro Enclaves are by reading the supporting documentation for this project, [About the AWS Nitro Enclaves Vault](https://aws-samples.github.io/sample-code-for-a-secure-vault-using-aws-nitro-enclaves/).

![nitro enclave architecture](https://aws-samples.github.io/sample-code-for-a-secure-vault-using-aws-nitro-enclaves/images/architecture.png)

**aws-genai-rfpassistant**

[aws-genai-rfpassistant](https://github.com/aws-samples/aws-genai-rfpassistant) this repository contains the code and infrastructure as code for a Generative AI-powered Request for Proposal (RFP) Assistant leveraging Amazon Bedrock and AWS Cloud Development Kit (CDK). This could be very hand if responding to RFP's is something that you do and you want to look at ways of optimising your approach. The documentation in the repo is very comprehensive. I have not tried this one out for myself, but I have been involved in both writing and reviewing RFPs in the past, so understand the pain that led to the creation of this project.

![example screenshot of the response to an rfp](https://github.com/aws-samples/aws-genai-rfpassistant/blob/main/assets/p15.png?raw=true)

**zero-downtime-deployment-tofu**

[zero-downtime-deployment-tofu](https://github.com/jorgetovar/zero-downtime-deployment-tofu) is a repo from AWS Community Build Jorge Tovar that contains code examples using OpenTofu that shows how you can achieve zero downtime using a number of different approaches. Check out the supporting blog post for more details, [Zero Downtime Deployment in AWS with Tofu/Terraform and SAM](https://dev.to/aws-builders/zero-downtime-deployment-in-aws-with-tofuterraform-and-sam-14d6). This is this weeks essential repo to check out, and a good opportunity to learn about and become familiar with the different techniques and options you have.

**streamlit-bedrock-claude-sample**

[streamlit-bedrock-claude-sample](https://github.com/garystafford/streamlit-bedrock-claude-sample) - I have featured Gary Stafford's open source projects and blog posts regularly in this newsletter. Gary has built a number of simple Streamlit applications to make it easy access the latest models and features of Amazon Web Services (AWS) Amazon Bedrock as part of several talks, workshops, and demonstrations he has done.  As part these, he has put together a simple Streamlit application that uses the Amazon Bedrock boto3 Python SDK to call the latest Anthropic Claude 3 family of multimodal foundation models. The application accepts a system and user prompt and generates a text-based response. The Streamlit app can be easily modified to incorporate new Bedrock features or as a starting point for your own applications.

**aws-chatbot-fargate-python**

[aws-chatbot-fargate-python](https://github.com/ran-isenberg/aws-chatbot-fargate-python) is a new repo from AWS Hero Ran Isenberg that deploys a Streamlit Chatbot in an AWS Fargate-based ESC cluster web application using AWS CDK (Cloud Development Kit). The infrastructure includes an ECS cluster, Fargate service, Application Load Balancer, VPC, and WAF and includes security best practices with CDK-nag verification. The chatbot is based on an implementation by Streamlit and the initial prompt is that the chatbot is me, Ran the builder, a serverless hero and attempts to answer as me. The Chatbot uses custom domain (you can remove it or change it to your own domain) and assume an OpenAI token exists in the account in the form of a secrets manager secret for making API calls to OpenAI.

**my-steampipe-arsenal**

[my-steampipe-arsenal](https://github.com/gabrielsoltz/my-steampipe-arsenal/blob/main/check-route53-inactive-alias.sql) Sometimes GitHub Gists or snippets are super useful, and Gabriel Soltz shares one such useful snippet in his repo of Steampipe queries that allows you to check for inactive Route53 alias'. Check out some of the other ones he shares too.


### AWS and Community blog posts

**This weeks essential reading**

* [The AWS SDK for Java 1.x is in maintenance mode, effective July 31, 2024](https://aws.amazon.com/blogs/developer/the-aws-sdk-for-java-1-x-is-in-maintenance-mode-effective-july-31-2024/) essential you read this if you are using the v1.x version of the AWS SDK for Java to find out what your options are, including test out the...
* [Preview Release of the Migration Tool for the AWS SDK for Java 2.x](https://aws.amazon.com/blogs/developer/preview-release-of-the-migration-tool-for-the-aws-sdk-for-java-2-x/) looks at how this tool might be able to help in migrating your 1.x application to 2.x. [hands on]
* [Amazon’s Exabyte-Scale Migration from Apache Spark to Ray on Amazon EC2](https://aws.amazon.com/blogs/opensource/amazons-exabyte-scale-migration-from-apache-spark-to-ray-on-amazon-ec2/) provides a fantastic look into what it takes to migrate from Apache Spark over to Ray at scale, and how this helped reduce both data processing time and cost - essential reading

![BDT’s initial high-level design for running compaction jobs with Ray on Amazon EC2](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2024/07/20/compaction-design.png)

**What I am reading from around the Community**

Each week I spent a lot of time reading posts from across the AWS community on open source topics. In this section I share what personally caught my eye and interest, and I hope that many of you will also find them interesting. It was really tough though, as there were so many great posts.

Starting things off this week is Muhammed Salih Guler, who shares how to build and deploy a Flutter web application using AWS Amplify in his post, [Deploy a Flutter Web Application Using AWS Amplify](https://salihgueler.medium.com/deploy-a-flutter-web-application-using-aws-amplify-68a3e4399716). One of my colleagues (Derek Bingham) has put together a bunch of Flutter content, and I have been meaning to try this out. I am going to give this a try over the weekend, so will let you know how I get on (watch out via socials).  I have been writing and play with Valkey over the past few weeks (check out some of my blog posts on this topic) and so found Dan Touitou's deep dive, [Unlock 1 Million RPS: Experience Triple the Speed with Valkey](https://valkey.io/blog/unlock-one-million-rps/), super interesting. Valkey 8.0 is available for folks to play with, and hopefully will go GA soon. I always have time to read up on robotics and IoT, so Mike's latest post, [Simulating Robots in the Cloud with EC2 and O3DE](https://community.aws/content/2jzQUoDbiUu8kSazQUdips5ZB8J/simulating-robots-in-the-cloud-with-ec2-and-o3de), shows you how you can speed up your robotic development using simulators, in this instance the Open 3D Engine (O3DE) open source project. Go check it out.

Next up we have a series of great blog posts covering all things AWS CDK from Pahud Hsieh. From diving deep into how grantRead works in the post, [What happens when bucket.grantRead() in AWS CDK](https://community.aws/content/2k0yQqU4HqYwTYteEStNVMbRRfZ/what-happens-when-bucket-grantread-in-cdk), or how you can begin contributing to the AWS CDK project in [Contributing to AWS CDK](https://community.aws/content/2jhmIXdVWZJy3uJnUfEzEmp652j/contributing-to-aws-cdk), dive deeper into more advanced CDK topics such as a look at some real-world use cases to override L1 props from L2 constructs in [Customize CDK L1 construct props from L2](https://community.aws/content/2kF5w7Bmwpob9wgqFMGJED5KJus/customize-cdk-l1-construct-props-from-l2). Pahud has also embraced generative AI, and shows how using tools like Amazon Q Developer (not open source sadly), you can use it to both create your CDK applications in [Writing CDK like a Pro using Amazon Q Customizations](https://community.aws/content/2jiAuQ0WB9fTInbfjgK9yXZt9f6/writing-cdk-like-a-pro-using-amazon-q-customizations), or how to build L2 CDK Construct Methods in [Generate CDK Construct Methods Using Amazon Q Customizations](https://community.aws/content/2kFFk3zU2sJsKQfIXT8Hs9LDqDG/generate-cdk-construct-methods-using-amazon-q-customizations). It's not only Pahud that has been creating CDK content though, my colleague Abhishek Gupta has also been exploring this topic in his latest blogging adventure, [Use AWS Generative AI CDK constructs to speed up app development](https://itnext.io/use-aws-generative-ai-cdk-constructs-to-speed-up-app-development-e032f3bb7adf) where he explores how to use the AWS Generative AI Constructs Library to deploy a complete RAG application.

I guess that is a good segway into a series of posts covering the latest open source libraries and frameworks for generative AI.  First up is Michele Ricciardi who shares how to enable prompt versioning and management, using LangChain and Amazon Bedrock Prompt management in his post, [Integrate Amazon Bedrock Prompt Management in LangChain applications](https://community.aws/content/2kPiIOekxM5O0kTGr9U3rgw183H/integrate-amazon-bedrock-prompt-manager-in-langchain-applications). Next up is a post from John Wick (yup, there was no way I was NOT going to post this right!) who shares how to work with generative AI in Javascript in his post, [GenAI, from your Local machine to AWS with LangChain.js](https://community.aws/content/2kPmdxeIrfBJKiCQtvVO8WvHWIZ/genai-from-your-local-machine-to-aws-with-langchain-js).

We conclude this round up with some cloud native posts, starting with Marcelo Andrade who shares how to find out which Kubernetes Pod owns a specific container in his post [From which Kubernetes pod (and namespace!) is this process that I see on my host? ](https://dev.to/aws-builders/from-which-kubernetes-pod-and-namespace-is-this-process-that-i-see-on-my-host-5c0n). I love these kinds of posts as they cover the things that I always need to know at some point (so I have bookmarked this for future reference). AWS Community Builder Saifeddine Rajhi shares how to use and run Argo Workflows to orchestrate jobs within your Kubernetes environments in the post, [Data on Kubernetes: Part 4 - Argo Workflows: Simplify parallel jobs : Container-native workflow engine for Kubernetes](https://dev.to/aws-builders/data-on-kubernetes-part-4-argo-workflows-simplify-parallel-jobs-container-native-workflow-engine-for-kubernetes-1fi4). This is part of a series which I found myself scrolling through, so check those other posts out too. Finally, we have AWS Community Builder Sunny Bhambhani shares how to get multiple helm charts installed in your Kubernetes clusters in his post, [Installing multiple helm charts in one go using simple bash utility](https://community.aws/content/2jgJ4HxHXquEZHqn6MQIpE8Ls0b/installing-multiple-helm-charts-in-one-go-using-simple-bash-utility).

**Cloud Native**

* [Automate monitoring for your Amazon EKS cluster using CloudWatch Container Insights](https://aws.amazon.com/blogs/infrastructure-and-automation/automate-monitoring-for-your-amazon-eks-cluster-using-cloudwatch-container-insights/) presents an event-driven, automation solution for monitoring your Amazon EKS cluster using Amazon CloudWatch Container Insights metrics as well as bunch of other AWS services and resources [hands on]

![Architectural overview of automation solution](https://d2908q01vomqb2.cloudfront.net/b7eb6c689c037217079766fdb77c3bac3e51cb4c/2024/07/30/eks-monitoring-07242024.png)

* [Diving into OCI Image and Distribution 1.1 Support in Amazon ECR](https://aws.amazon.com/blogs/opensource/diving-into-oci-image-and-distribution-1-1-support-in-amazon-ecr/) looks into how Amazon ECR is one of the first registry cloud services to support the Referrers API and OCI 1.1 (read the post to find out what that means!)
* [Cordial’s journey implementing Bottlerocket and Karpenter in Amazon EKS](https://aws.amazon.com/blogs/containers/cordials-journey-implementing-bottlerocket-and-karpenter-in-amazon-eks/) is a case study in how Cordial implemented Bottlerocket as the Operating System (OS) and Karpenter as the Node Lifecycle Manager within their Amazon EKS environments to achieve operational efficiency and improve security posture (graphs ahoy!)
* [How Getir optimized their Amazon EKS compute using Karpenter](https://aws.amazon.com/blogs/containers/how-getir-optimized-their-amazon-eks-compute-using-karpenter/) provides another case study, this time Getir, and how Karpenter helped them address the challenges of spiky workloads, which require faster responses for dynamic scaling
* [Developing Custom Processors using OpenTelemetry in .NET 8](https://aws.amazon.com/blogs/dotnet/developing-custom-processors-using-opentelemetry-in-net-8/) explores how to develop a custom processor using OpenTelemetry in the .NET ecosystem [hands on]
* [Making sense of secrets management on Amazon EKS for regulated institutions](https://aws.amazon.com/blogs/security/making-sense-of-secrets-management-on-amazon-eks-for-regulated-institutions/) provides a summary of three options for managing secrets in Amazon EKS - ESO, Sealed Secrets, and AWS Secrets and Configuration Provider (ASCP), and the key considerations for FSI customers when choosing between them
* [How to Run WebAssembly on Amazon EKS](https://aws.amazon.com/blogs/containers/16532-2/) is a step by step guid on how AWS empowers users to harness the full potential of Wasm by providing a seamless integration with Amazon EKS [hands on]

**Data and Analytics**

* [Build a real-time analytics solution with Apache Pinot on AWS](https://aws.amazon.com/blogs/big-data/build-a-real-time-analytics-solution-with-apache-pinot-on-aws/)  shows how to deploy a scalable Apache Pinot-based near real-time user facing analytics solution on AWS [hands on]
* [Stream change data in a multicloud environment using AWS DMS, Amazon MSK, and Amazon Managed Service for Apache Flink](https://aws.amazon.com/blogs/database/stream-change-data-in-a-multicloud-environment-using-aws-dms-amazon-msk-and-amazon-managed-service-for-apache-flink/) dives deep into architecture, approaches, and considerations for streaming data changes from the transactional databases deployed in other cloud providers to a streaming data solution deployed on AWS [hands on]

![architecture for streaming changes across multi-clouds](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2024/08/02/dbblog-3456-image001-1024x374.png)

* [Improve the resilience of Amazon Managed Service for Apache Flink application with system-rollback feature](https://aws.amazon.com/blogs/big-data/improve-the-resilience-of-amazon-managed-service-for-apache-flink-application-with-system-rollback-feature/) looks at how to use the system-rollback feature in Managed Service for Apache Flink, and  how this functionality improves your application’s resilience by providing a highly available Flink application [hands on]
* [Build and deploy knowledge graphs faster with RDF and openCypher](https://aws.amazon.com/blogs/database/build-and-deploy-knowledge-graphs-faster-with-rdf-and-opencypher/) shows you how to use openCypher with RDF graphs [hands on]
* [Monitoring Apache Iceberg metadata layer using AWS Lambda, AWS Glue, and AWS CloudWatch](https://aws.amazon.com/blogs/big-data/monitoring-apache-iceberg-metadata-layer-using-aws-lambda-aws-glue-and-aws-cloudwatch/) discusses how the metadata layer of Apache Iceberg can be used to make data lakes more efficient. You will learn about an open-source solution that can collect important metrics from the Iceberg metadata layer [hands on]

![apache iceberg metadata layers](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2024/07/22/BDB-3503-iceberg-arch-1024x574.png)

* [Integrate Amazon MWAA with Microsoft Entra ID using SAML authentication](https://aws.amazon.com/blogs/big-data/integrate-amazon-mwaa-with-microsoft-entra-id-using-saml-authentication/) illustrates how to configure an Amazon MWAA environment deployed in private network access mode with customer managed VPC endpoints and authenticate users using SAML federated identity using Microsoft Entra ID and Application Load Balancer (ALB) [hands on]

![overview of MWAA SAML authentication architecture with Entra ID](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2024/07/17/01-architecture.png)

* [Optimize cost and performance for Amazon MWAA](https://aws.amazon.com/blogs/big-data/optimize-cost-and-performance-for-amazon-mwaa/) provides guidance on how you can optimise performance and save cost of your Apache Airflow environments by following some good practices [hands on]
* [How Amazon GTTS runs large-scale ETL jobs on AWS using Amazon MWAA](https://aws.amazon.com/blogs/big-data/how-amazon-gtts-runs-large-scale-etl-jobs-on-aws-using-amazon-mwaa/) is a great case study on how Amazon GTTS were able to see 70% improvement in end-to-end runtime on their ETL jobs, among other benefits - a great read

![Amazon GTTS MWAA architecture](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2024/05/22/BDB-3453-image011.jpg)

* [Synchronize data lakes with CDC-based UPSERT using open table format, AWS Glue, and Amazon MSK](https://aws.amazon.com/blogs/big-data/synchronize-data-lakes-with-cdc-based-upsert-using-open-table-format-aws-glue-and-amazon-msk/) illustrates the construction of a comprehensive CDC system, enabling the processing of CDC data sourced from an Amazon RDS for MySQL source [hands on]
* [Improve Apache Kafka scalability and resiliency using Amazon MSK tiered storage](https://aws.amazon.com/blogs/big-data/improve-apache-kafka-scalability-and-resiliency-using-amazon-msk-tiered-storage/) dives deep into how tiered storage helps with faster broker recovery and quicker partition migrations, facilitating faster load balancing and broker scaling in your Apache Kafka clusters (plenty of graphs in this one!)
* [AWS Glue mutual TLS authentication for Amazon MSK](https://aws.amazon.com/blogs/big-data/aws-glue-mutual-tls-authentication-for-amazon-msk/) describes how to set up AWS Glue jobs to produce, consume, and process messages on an MSK cluster using mutual TLS authentication [hands on]
* [Migrate an on-premises MySQL database to Amazon Aurora MySQL over a private network using AWS DMS homogeneous data migration and Network Load Balancer](https://aws.amazon.com/blogs/database/migrate-an-on-premises-mysql-database-to-amazon-aurora-mysql-over-a-private-network-using-aws-dms-homogeneous-data-migration-and-network-load-balancer/) guides you through the steps of performing a homogeneous migration from an on-premises MySQL database to Amazon Aurora MySQL using AWS DMS homogeneous data migrations over a private network using network load balancer [hands on]
* [Implement a rollback strategy after an Amazon Aurora MySQL blue/green deployment switchover](https://aws.amazon.com/blogs/database/implement-a-rollback-strategy-after-an-amazon-aurora-mysql-blue-green-deployment-switchover/) looks at the steps needed to perform a blue/green deployment switchover and how to set up and perform a rollback strategy post switchover for Amazon Aurora MySQL-Compatible Edition [hands on]
* [Build a serverless data quality pipeline using Deequ on AWS Lambda](https://aws.amazon.com/blogs/big-data/build-a-serverless-data-quality-pipeline-using-deequ-on-aws-lambda/) shows how to run Deequ (an open source framework for data quality) on Lambda [hands on]
* [Build a custom HTTP client in Amazon Aurora PostgreSQL and Amazon RDS for PostgreSQL: An alternative to Oracle’s UTL_HTTP](https://aws.amazon.com/blogs/database/build-a-custom-http-client-in-amazon-aurora-postgresql-and-amazon-rds-for-postgresql-an-alternative-to-oracles-utl_http/) is a neat post that demonstrates how you can use PL/pgSQL custom wrapper functions to convert Oracle UTL_HTTP referenced custom code to the Amazon Aurora PostgreSQL and Amazon RDS for PostgreSQL equivalent [hands on]

**Other posts to check out**

* [From Data Chaos to Cohesion: How OCSF is Optimizing Cyber Threat Detection](https://aws.amazon.com/blogs/opensource/from-data-chaos-to-cohesion-how-ocsf-is-optimizing-cyber-threat-detection/)  is an in depth overview of the OCSF’s progress since its inception in 2022, and share insights from organisations participating in the project and adopting OCSF
* [GraphStorm 0.3: Scalable, multi-task learning on graphs with user-friendly APIs](https://aws.amazon.com/blogs/machine-learning/graphstorm-0-3-scalable-multi-task-learning-on-graphs-with-user-friendly-apis/) provides an overview of what GraphStorm is and how it can help you tackle your large-scale graph ML challenges [hands on]
* [Installing Red Hat OpenShift on AWS in a restricted network using AWS Secure Token Service](https://aws.amazon.com/blogs/ibm-redhat/installing-red-hat-openshift-on-aws-in-a-restricted-network-using-aws-secure-token-service/) is a detailed walk through on how to install a Red Hat OpenShift Container Platform cluster in a restricted Amazon VPC network to comply with regulatory requirements and organisational controls [hands on]

![Network architecture to deploy OpenShift in a restricted Amazon VPC](https://d2908q01vomqb2.cloudfront.net/c097638f92de80ba8d6c696b26e6e601a5f61eb7/2024/07/26/Network-architecture-to-deploy-OpenShift-in-a-restricted-Amazon-VPC-1024x420.jpg)

* [How DXC creates application consistent EBS Snapshots for Linux](https://aws.amazon.com/blogs/storage/how-dxc-creates-application-consistent-ebs-snapshots-for-linux/) looks at how DXC and AWS collaborated to implement a serverless solution to create application consistent backups for Linux instances [hands on]

### Quick updates

**Karpenter**

Karpenter’s APIs graduate out of beta with the release of Karpenter version 1.0.0. Karpenter is a flexible, efficient, and high-performance Kubernetes compute management solution that helps improve application availability, reduce operational overhead, and increase cluster compute utilisation. This release also includes three new features which provide customers greater control over how and when Karpenter disrupts Kubernetes applications. Customers can use Karpenter with Amazon Elastic Kubernetes Service (EKS) or any conformant Kubernetes cluster. Like other Kubernetes open-source projects, Karpenter’s APIs follow a maturity progression from alpha to beta then stable. In October 2023, the Karpenter project graduated its APIs from alpha to beta. This release marks the final milestone in the project’s maturity and customers can be assured that all Karpenter APIs will remain available in future 1.0 minor versions and not modified in any way that results in breaking changes. Alongside the graduation from beta, this 1.0 release includes three new features for Karpenter: 1/ the ability to specify disruption reasons, e.g. underutilisation, emptiness, drift, for disruption budgets, 2/ a forceful disruption mode that helps customers balance application availability against security requirements, and 3/ an expansion of consolidateAfter which lets customers better tune Karpenter’s consolidation feature to meet their cost-efficiency and application availability requirements.

Alex Kestner, Robert Northard, and Rajdeep Saha share more details in the post, [Announcing Karpenter 1.0](https://aws.amazon.com/blogs/containers/announcing-karpenter-1-0/)

**MySQL**

Amazon Relational Database Service (Amazon RDS) for MySQL now supports MySQL minor version 8.0.39. We recommend that you upgrade to the latest minor versions to fix known security vulnerabilities in prior versions of MySQL, and to benefit from the bug fixes, performance improvements, and new functionality added by the MySQL community. Learn more about the enhancements in RDS for MySQL 8.0.39 in the Amazon RDS user guide.

Amazon RDS for MySQL now supports version 8.4 in the Amazon RDS Database Preview Environment, allowing you to evaluate the latest Long-Term Support Release on Amazon RDS for MySQL. You can deploy MySQL 8.4 in the Amazon RDS Database Preview Environment that has the benefits of a fully managed database, making it simpler to set up, operate, and monitor databases. MySQL 8.4 is the latest Long-Term Support Release from the MySQL community.

**PostgreSQL**

There were a number of PostgreSQL related updates since the last newsletter. Here are the highlights:

Amazon Aurora PostgreSQL-Compatible Edition now supports PostgreSQL versions 16.3, 15.7, 14.12, 13.15, and 12.19. These releases contain product improvements and bug fixes made by the PostgreSQL community, along with Aurora-specific improvements. Databases now startup faster after upgrades and restarts. Version 16.3 with IO-Optimized configuration includes performance enhancements that improve write throughput for 8xl and larger instances. These releases also contain Babelfish’s new features and improvements such as support for group AD, logical replication, Blue/Green Deployments, and LIKE operator for AI collations. As a reminder, Amazon Aurora PostgreSQL 12 support ends on Feb 29, 2025. Upgrade to a newer major version. You can initiate a minor version upgrade by modifying your DB cluster.

Amazon Aurora PostgreSQL-Compatible Edition now supports pgvector 0.7.0, an open-source extension for PostgreSQL for storing vector embeddings in your database. pgvector provides vector similarity search capabilities enabling Aurora usage for semantic search and retrieval-augemented generation (RAG) in generative artificial intelligence (AI) applications. pgvector 0.7.0 adds parallelism to improve the Hierarchical Navigable Small Worlds (HNSW) index build time in Aurora. pgvector 0.7.0 adds two new vector data types: halfvec for storing dimensions as 2-byte floats, and sparsevec for storing up to 1,000 nonzero dimensions, and now supports indexing binary vectors using the PostgreSQL-native bit type. These additions let you use scalar and binary quantization for the vector data type using PostgreSQL expression indexes, which reduces index storage size and lowers index build time. Quantization also lets you increase the maximum dimensions of vectors you can index: 4,000 for halfvec and 64,000 for binary vectors. pgvector 0.7.0 is available in Amazon Aurora clusters running PostgreSQL 16.3, 15.7, 14.12, 13.15, and 12.19 and higher in all applicable AWS Regions.

Amazon RDS for PostgreSQL 17 Beta 3 is now available in the Amazon RDS Database Preview Environment, allowing you to evaluate the pre-release of PostgreSQL 17 on Amazon RDS for PostgreSQL. You can deploy PostgreSQL 17 Beta 3 in the Amazon RDS Database Preview Environment that has the benefits of a fully managed database. PostgreSQL 17 includes updates to vacuuming that reduces memory usage, improves time to finish vacuuming, and shows progress of vacuuming indexes. With PostgreSQL 17, you no longer need to drop logical replication slots when performing a major version upgrade. PostgreSQL 17 continues to build on the SQL/JSON standard, adding support for `JSON_TABLE` features that can convert JSON to a standard PostgreSQL table. The `MERGE` command now supports the `RETURNING` clause, letting you further work with modified rows. PostgreSQL 17 also includes general improvements to query performance and adds more flexibility to partition management with the ability to SPLIT/MERGE partitions.

Amazon Relational Database Service (RDS) for PostgreSQL now supports the latest minor versions 16.4, 15.8, 14.13, 13.16, and 12.20. This release of RDS for PostgreSQL also includes updates for PostgreSQL extensions such as pgvector 0.7.3, hypopg 1.4.1, and others.

**Amazon EMR**

Amazon EMR 7.2 release is now generally available and includes Apache Spark 3.5.1, Trino 436, and PrestoDB 0.285, Apache Iceberg 1.5.0 and Delta 3.1. Furthermore, with Amazon EMR 7.2, you can view additional Amazon CloudWatch metrics for enhanced monitoring in the Amazon EMR console, which provides comprehensive monitoring capabilities, allowing you to track the performance and health of your cluster more effectively. You can configure the Amazon CloudWatch Agent to publish metrics for Apache Hadoop, YARN, and Apache HBase applications running on your Amazon EMR on EC2 clusters, and track the metrics of each cluster within the EMR console. In addition, Amazon EMR 7.2 adds support for Apache Flink Operator 1.8 with Amazon EMR on EKS.

**ActiveMQ**

Amazon MQ now supports ActiveMQ minor version 5.18, which introduces several improvements and fixes compared to the previous version of ActiveMQ supported by Amazon MQ. These enhancements include initial support for the JMS 2.0 simplified APIs, such as JMSContext, JMSProducer, and JMSConsumer, as well as the implementation of methods for XA transactions. Starting from ActiveMQ 5.18, Amazon MQ will manage patch version upgrades for your brokers. All brokers on ActiveMQ version 5.18 will be automatically upgraded to the next compatible and secure patch version in your scheduled maintenance window. If you are utilising prior versions of ActiveMQ, such as 5.17, 5.16, or 5.15, we strongly recommend you to upgrade to ActiveMQ 5.18. You can easily perform this upgrade with just a few clicks in the AWS Management Console.

**Red Hat Enterprise Linux**

Amazon AppStream 2.0 now offers support for Red Hat Enterprise Linux, enabling ISVs and central IT organisations to stream Red Hat Enterprise Linux apps and desktops to users while leveraging the flexibility, scalability, and cost-effectiveness of the AWS Cloud. With this launch, customers have the flexibility to choose from a broader set of operating systems including Red Hat Enterprise Linux, Amazon Linux 2, and Microsoft Windows. This launch enables organisations operating in highly regulated industries to accelerate time to market, scale resources up or down with demand, and manage the entire fleet centrally through the AWS Console by streaming Red Hat Enterprise Linux apps from AppStream 2.0. Red Hat Enterprise Linux on AppStream 2.0 also enables traditional desktop apps to be converted to a SaaS delivery model without the cost of refactoring, while pay-as-you-go billing and license-included images ensure you only pay for the resources you use. Red Hat Enterprise Linux is currently supported in all AWS Regions where AppStream 2.0 is available. Red Hat Enterprise Linux-based instances use per second billing (with a minimum of 15 minutes).

Check out this related post, [Announcing Red Hat Enterprise Linux 8 on Amazon WorkSpaces and Amazon AppStream 2.0](https://aws.amazon.com/blogs/desktop-and-application-streaming/announcing-red-hat-enterprise-linux-8-on-amazon-workspaces-and-appstream-2-0/)

### Videos of the week

**Getting Started with OpenTofu in AWS**

In this video Chris Hill shows you how to provision infrastructure, manage state effectively, and implement best practices for automation. We'll also cover importing existing resources into OpenTofu to optimise your cloud management. You can follow along with supporting code.

{{< youtube atSuG8nkVac >}}


**An Intro to AWS Deployments with OpenTofu, Scalr, & GitHub!**

Keeping with the OpenTofu theme, David Hundley does a live coding session that covers using OpenSearch as a vector store for a RAG solution, using OpenTofu as the infrastructure as code layer to simplify deployment.

{{< youtube UQ2A0I0THtY >}}

**Cedar Policies: Default Deny and Avoiding Evaluation Errors with Validation**

A new video from Cedar Craft, a series of brilliant short videos that walk you through key concepts of Cedar and then shows you how these work with hands on code examples. In this latest video, they look at Policy errors. Policies that error can be difficult to reason about. We should a small example here where two seemingly equivalent policies give different answers if you make the "same" mistake in both. The fix is easy though: always validate your policies!

{{< youtube aHFCjqONbxI >}}

### Events for your diary

If you are planning any events in 2024, either virtual, in person, or hybrid, get in touch as I would love to share details of your event with readers. 


**Open Source Summit**
**September 16-18th, Vienna, Austria**

Come join my colleagues at the AWS booth at the Open Source Summit Europe, which is being held in the wonderful city of Vienna. There will be a bunch of around, doing talks, open source technology demos, and just hanging out with the open source community. Be great to see some of you there.

**All Things Open**
**27-29th October, Raleigh, North Carolina**

Make sure you attend All Things Open this coming Autumn if you can, it is one of my favourite tech conferences, with the amazing community that comes year in, year out. As always my colleagues will be manning the AWS booth, and I am sure we will have some cool stuff and SWAG to share with the community.

Check out and grab your ticket while they are still available at [2024.allthingsopen.org](https://2024.allthingsopen.org/)

**Manchester Tech Festival**
**29th October**

I will be speaking about Cedar at the [Manchester Tech Festival](https://www.manchestertechfestival.co.uk/cyber-security/) in October. Looking forward to sharing info about Cedar with the local developers attending. Hope to see some of you there. 


**Cortex**
**Every other Thursday, next one 16th February**

The Cortex community call happens every two weeks on Thursday, alternating at 1200 UTC and 1700 UTC. You can check out the GitHub project for more details, go to the [Community Meetings](https://github.com/cortexproject/cortex#community-meetings) section. The community calls keep a rolling doc of previous meetings, so you can catch up on the previous discussions. Check the [Cortex Community Meetings Notes](https://docs.google.com/document/d/1shtXSAqp3t7fiC-9uZcKkq3mgwsItAJlH6YW6x1joZo/edit) for more info.

**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://www.meetup.com/OpenSearch/)

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes: Jorge Tovar, Gabriel Soltz, Eduardo Monich Fronza, Rishit G Barochia, Steve Mirman, Sunil Gajula, Michael Greenshtein, Dan Garibay, Matthew Miller, Manish Garg, Navdeep Pareek, Sushant Jagdale, Satya Chikkala, Vijay Velpula, Sriharsh Adari, Jeetendra Vaidya, Retina Satish, Shubham Purwar, Nitin Kumar, Patrick Ames, Jules Damji, Zhe Zhang, Jesse Butler, Michael Brown, Sai Maddali, Masudur Rahaman Sayem, Nagarjuna Koduru, Xiang Song, Florian Saupe, Jian Zhang, Alok Srivastava, A. Mosaad, Asif Fouzi, Prahal N P, Daxeshkumar Patel, Bhavesh Rathod, Kamal Singh, Raj Ramasubbu, Francisco Morillo, Ismail Makhlouf, Edward Ondari, Emmanuel Mashandudze, Sai Charan Teja Gopaluni, Daniel Schaaff, Martin Guy Lapointe, Neelendra Bhandari, Richard Kelly, Nisha Gambhir, Bibhuti Sahu, Mayank Kumar, Simran Singh, Amandeep Bajwa, Deevanshu Budhiraja, Sasha Luthra, Ora Lassila, Charles Ivie, Willem Broekema, Michael Schmidt,Piyush Mattoo, Chetan Pawar, Ruy Cavalcanti, Alex Koenig, David Surey, Bhanu Ganesh Gudivada, Vamsikrishna Jammula, Rajeshkumar Sabankar, Sumana Yanamandra, Alejandro Velez, Danny Steenman, Gary Stafford, Muhammed Salih Guler, Dan Touitou, Pahud Hsieh, Abhishek Gupta, Michele Ricciardi, John Wick, Saifeddine Rajhi, Sunny Bhambhani, and Marcelo Andrade.

**Feedback**

Please please please take 1 minute to [complete this short survey](https://www.pulse.aws/promotion/10NT4XZQ). 

### Stay in touch with open source at AWS

Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) for more open source goodness.

One of the pieces of feedback I received in 2023 was to create a repo where all the projects featured in this newsletter are listed. Where I can hear you all ask? Well as you ask so nicely, you can meander over to[ newsletter-oss-projects](https://github.com/094459/newsletter-oss-projects).

Made with ♥ from DevRel