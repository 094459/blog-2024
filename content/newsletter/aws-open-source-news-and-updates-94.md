---
title: 'AWS open source news and updates #94'
date: '2021-12-20'
tags : [ oss-newsletter , AWS Open Source]
---
## December 20th, 2021 - Instalment #94

Newsletter #94. 

This will be the last newsletter  of 2021 before I break for Christmas and New Year. I hope you have found this newsletter a useful resource for finding out about new or interesting open source projects, both from what AWS contributes to, but also from the wider builder and open source developer communities.

To finish up for 2021 we have more new open source projects, covering Amazon Location Services, AWS Fault Injection Simulator (FIS) experiment templates that are AWS CDK ready, Media Replay Engine (MRE)a really nice project to help you automate the creation of replays, a transcribe, post call analytics solution and more. We also have some great content covering Apache Airflow, Apache Flink, Hugging Face, ROS, Apache HBase, Apache Spark, ActiveMQ, PyTorch, ROSA, Argo Rollouts, lots of Kubernetes related posts and more.

Finally, make sure you check out the videos, where we have a really great story that combines AWS DeepRacer with a rodent problem. Really cool stuff.

To start however, I just want to share some important updates about Apache Log4j.

**Apache Log4j rce update**

We have been working very hard to help customers understand how to work through this incident. Here are some resources that you should check out, including a number of tools that you might find helpful.

* [Hotpatch for Apache Log4j](https://aws.amazon.com/blogs/opensource/hotpatch-for-apache-log4j/)- this is a blog post published that provides some general information as well as access to some tooling that can help customers identify and patch systems that may be vulnerable. For customers who are using Amazon Linux 2, you can now install this quickly (https://twitter.com/stewartsmith/status/1471150310718468097) via “yum install log4j-cve-2021-44228-hotpatch” as it has been added to the package repositories.
* [Open source hotpatch for Apache Log4j vulnerability](https://aws.amazon.com/blogs/security/open-source-hotpatch-for-apache-log4j-vulnerability/) - AWS CISO Steve Schmidt summarised our efforts/position on this, pointing to the same resource above. 
* [hotpatch-for-apache-log4j2](https://github.com/corretto/hotpatch-for-apache-log4j2) - This is a tool which injects a Java agent into a running JVM process. The agent will attempt to patch the lookup() method of all loaded org.apache.logging.log4j.core.lookup.JndiLookup instances to unconditionally return the string "Patched JndiLookup::lookup()".
* [kubernetes-log4j-cve-2021-44228-node-agent](https://github.com/aws-samples/kubernetes-log4j-cve-2021-44228-node-agent) - The Apache Log4j2 CVE-2021-44228 node agent is an open source project built by the Kubernetes team at AWS. It is designed to run as a DaemonSet and mitigate the impact of Log4j2 CVE-2021-44228
* [Using AWS security services to protect against, detect, and respond to the Log4j vulnerability](https://aws.amazon.com/blogs/security/using-aws-security-services-to-protect-against-detect-and-respond-to-the-log4j-vulnerability/) - a guide on how to use AWS security services to help you manage this incident.
* [Advice on mitigating the Apache log4j security issue for EKS, ECS, and Fargate customers](https://aws.amazon.com/blogs/containers/advice-on-mitigating-the-apache-log4j-security-issue-for-eks-ecs-and-fargate-customers/)- this post  shows you how Amazon Elastic Container Service (Amazon ECS) and Amazon Elastic Kubernetes Service (Amazon EKS) customers using Amazon EC2 and AWS Fargate to run their containerized applications can identify and mitigate CVE-2021-44228 and CVE-2021-45046 (the “log4j2 issue”).
* [Container scanning updates in Amazon ECR private registries using Amazon Inspector](https://aws.amazon.com/blogs/containers/container-scanning-updates-in-amazon-ecr-private-registries-using-amazon-inspector/) - if you create/build/use container images, then check out how you can scan those to help identify vulnerabilities such as CVE-2021-44228 and CVE-2021-45046. 

**Job Alert**

This position is still open, and if you are looking for a fresh start to 2020 then read on.  What are we looking for? We are looking for someone who will be responsible for defining, leading, and contributing to the open source and community engagement content strategy for the services and technology teams across AWS. You will combine your passion and enthusiasm for cloud technology and open source with your unmatched creativity to generate content and support for AWS among key open source communities, industry opinion makers, and technologists.

You will work closely with the product marketing leadership to translate the business priorities of the service teams into original content for a variety of audiences, including C-level, end users, developers, managers, and engineers.

Ideally, you are already a recognisable figure in the open source ecosystem, in demand to contribute to technical and business publications, with an exemplary presence on social media.

Here is the Job Spec, [Principal Evangelist, Open Source, Open Source Strategy & Marketing](https://www.amazon.jobs/en/jobs/1821512/principal-evangelist-open-source-open-source-strategy-marketing) where you can read more and see how to apply.

### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Rajarshi Das, Yasunori Kirimoto, Adam Cerin, Adrian Hornsby, John Gramila, Eira May, Ryan Donovan, Martin Paradesi, Vincent Gromakowski, Gary Stafford, Balasubramanian Sakthivel, Victor Gan, Manjula Nagineni, Amir Shenavandeh, Maryam Tavakoli, Laurence Miao, Srinivasa Shaik, Matt Aylward, Sasi Jayalekshmi, Suranjan Choudhury, Anil Sharma, Imaya Kumar Jagannathan, Michael Hausenblas, Bob Strahan, Andrew Kane, Connor Kirkpatrick, Franco Rezabek, and Steve Engledow.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest open source projects

**amazon-location-service-starter**

[amazon-location-service-starter](https://github.com/dayjournal/amazon-location-service-starter) this is a starter open source project from Yasunori Kirimoto that gets you started with Amazon Location Service using a number of AWS Services and open source projects - AWS Amplify, MapLibre GL JS Amplify, MapLibre GL JS, webpack.

![demo](https://github.com/dayjournal/amazon-location-service-starter/blob/main/img/README01.gif?raw=true)

**aws-media-replay-engine**

[aws-media-replay-engine](https://github.com/awslabs/aws-media-replay-engine) this Apache 2.0 project, Media Replay Engine (MRE) is a framework to build automated video clipping and replay (highlight) generation pipelines for live and video-on-demand content. Nice detailed docs, including some guidelines on costs, make sure you check out this project.

![arch](https://github.com/awslabs/aws-media-replay-engine/blob/main/docs/assets/images/MRE_Architecture.png?raw=true)

**aws-fis-templates-cdk**

[aws-fis-templates-cdk](https://github.com/adhorn/aws-fis-templates-cdk) chatting last week with Adrian Hornsby before he spends some time in the artic circle, he shared with me this repo that contains a collection of AWS Fault Injection Simulator (FIS) experiment templates deploy-able via with the AWS CDK. These templates let you perform fault injection experiments on resources (applications, network, and infrastructure) in the AWS Cloud.

**aws-securityhub-falco-ecs-eks-integration**

[aws-securityhub-falco-ecs-eks-integration](https://github.com/aws-samples/aws-securityhub-falco-ecs-eks-integration) this repo deploys a Lambda function, that enables generating Falco findings into Security Hub. To walk you through this, Rajarshi Das and Adam Cerin have put together this post, [Continuous runtime security monitoring with AWS Security Hub and Falco](https://aws.amazon.com/blogs/security/continuous-runtime-security-monitoring-with-aws-security-hub-and-falco/)

![arch](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2021/12/09/image1-v2-1.jpg)

**amazon-transcribe-post-call-analytics**

[amazon-transcribe-post-call-analytics](https://github.com/aws-samples/amazon-transcribe-post-call-analytics) This open source sample solution, Post Call Analytics (PCA), does most of the heavy lifting associated with providing an end-to-end solution that can process call recordings from your existing contact center. Bob Strahan, Andrew Kane, Connor Kirkpatrick, Franco Rezabek, and Steve Engledow have collaborated on this post, [Post call analytics for your contact center with Amazon language AI services](https://aws.amazon.com/blogs/machine-learning/post-call-analytics-for-your-contact-center-with-amazon-language-ai-services/) to help you get started.

![arch](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2021/12/16/ML-5919-image009.png)

**poro**

[poro](https://github.com/9rnt/poro) this script lets you scan publicly accessible assets on your AWS cloud environment for reporting. purposes. Might come in handy for folks that are looking to do this.

### AWS and Community blog posts

**AWS BugBust**

Earlier in the year, we announced BugBust - a worldwide competition to help find and fix bugs in Java and Python applications. During re:Invent, there was an attempt to set a Guinness World Record for the largest bug fixing challenge. I don't want to spoil the surprise, so check out this write up from Eira May and Ryan Donovan, [Smashing bugs to set a world record: AWS BugBust](https://stackoverflow.blog/2021/12/09/smashing-bugs-to-set-a-world-record-aws-bugbust/)

**Amazon EMR**

When it comes to saving money, I am all ears. I therefore was very thankful to John Gramila for putting together, [AWS EMR Cost Optimization Guide](https://www.cloudforecast.io/blog/aws-emr-cost-optimization-guide/). If you are using or planning to use Amazon EMR, then make sure you check out some of the tips in this post to help you optimise your costs.

**ROS**

Camilo Buscaron shares news that we have added the supporting software and simulation artefacts to integrate the AWS DeepRacer Evo 64 device software with ROS Nav2 stack, and made it available to the open source community via the AWS DeepRacer GitHub in his post, [Integrating ROS Nav2 stack with AWS DeepRacer](https://discourse.ros.org/t/integrating-ros-nav2-stack-with-aws-deepracer/23481)

![demo](https://aws1.discourse-cdn.com/business7/uploads/ros/original/2X/8/8cc365fd7820546e100662dda1da851c2af7234b.gif)

**Grafana**

In case you missed it, there were a number of nice announcements during pre:Invent and re:Invent for customers who are interested in Grafana. Imaya Kumar Jagannathan and Michael Hausenblas have summarised these in the post, [Amazon Athena, Amazon Redshift Plugins and New Features in Amazon Managed Grafana](https://aws.amazon.com/blogs/mt/amazon-athena-amazon-redshift-plugins-and-new-features-in-amazon-managed-grafana/) walking you through the Geomap visualisation, Amazon Redshift data source, CloudWatch Metrics Insights, and interestingly, IoT TwinMaker integration (which is in preview). Lots to digest, so make sure you check this out.

![demo](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2021/12/15/image.jpg)

**Apache Airflow**

A couple of posts you should check out this week. 

First up, we have Gary Stafford who writes, [DevOps for DataOps: Building a CI/CD Pipeline for Apache Airflow DAGs](https://garystafford.medium.com/devops-for-dataops-building-a-ci-cd-pipeline-for-apache-airflow-dags-975e4a622f83) showing you how you can use GitHub Actions to build an effective CI/CD workflow for our Apache Airflow DAGs. 

![arch](https://miro.medium.com/max/1400/0*FNlH8rIaRbK40tty)

Following that we have a short post from myself, [Setting up MWAA to use a KMS key](https://dev.to/aws/setting-up-mwaa-to-use-a-kms-key-4p6b) where I walk you through how to configure your Managed Workflows for Apache Airflow to use a customer defined KMS key so that you can encrypt everything within your Airflow environment.

**Apache Flink**

In this post [How Goldman Sachs built persona tagging using Apache Flink on Amazon EMR](https://aws.amazon.com/blogs/big-data/how-goldman-sachs-built-persona-tagging-using-apache-flink-on-amazon-emr/), Balasubramanian Sakthivel, Victor Gan, and Manjula Nagineni share with you how Goldman Sachs built a system using Apache Flink on Amazon EMR to carry out the tagging of users with various personas, in order to better curate content offerings for those users.

![arch](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2021/12/08/Persona-Tagging-1.png)

**Apache Spark**

Vincent Gromakowski shares [Best practices for running Spark on Amazon EKS](https://aws.amazon.com/blogs/containers/best-practices-for-running-spark-on-amazon-eks/) where you will learn how to configure Apache Spark and Amazon EKS to support common requirements, including resources isolation, cost reduction, dynamic scaling, performance optimisation, and fine-grained access control.

**Apache HBase**

Apache HBase is a popular, open source non-relational database. One of the typical use cases where you find it being used, is when you need random, realtime read/write access to your Big Data -  the project's goal is the hosting of very large tables, billions of rows X millions of columns. In this post, [Stream Apache HBase edits for real-time analytics](https://aws.amazon.com/blogs/big-data/stream-apache-hbase-edits-for-real-time-analytics/) Amir Shenavandeh and Maryam Tavakoli walk you through Apache HBase scaling and replication concepts before sharing some common use cases and solutions, along with some best practices when implementing your custom HBase streaming replication endpoints.

![arch](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2021/12/03/BDB-1445-image004.png)

**PyTorch**

Laurence Miao shares how to [Build GAN with PyTorch and Amazon SageMaker](https://aws.amazon.com/blogs/machine-learning/build-gan-with-pytorch-and-amazon-sagemaker/), and he walks you through building your first GAN model using Amazon SageMaker, learning GANs from the perspective of practical engineering experiences, as well as opening a new AI/ML domain of generative models. The post also introduces a use case of one of the hottest GAN applications in the synthetic data generation area. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2021/11/11/ML-6149-image023.jpg)

For more PyTorch content, check out the links below for "Build custom Amazon SageMaker PyTorch models for real-time handwriting text recognition"

**Argo Rollouts**

Argo Rollouts is a Kubernetes controller and set of CRDs which provide advanced deployment capabilities such as blue-green, canary, canary analysis, experimentation, and progressive delivery features to Kubernetes. Srinivasa Shaik, Matt Aylward, and Sasi Jayalekshmi have collaborated on the post, [Use Amazon EKS and Argo Rollouts for Progressive Delivery](https://aws.amazon.com/blogs/architecture/use-amazon-eks-and-argo-rollouts-for-progressive-delivery/) showing you how when you implement a progressive delivery controller (via Argo Rollouts) in conjunction with AWS services, you can tune the speed of your deployments and measure your success with KPIs. 

![arch](https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2021/12/13/Fig1-blgrdeploy.png)

**ActiveMQ**

Suranjan Choudhury and Anil Sharma have come together to write [Using an Amazon MQ network of broker topologies for distributed microservices](https://aws.amazon.com/blogs/compute/using-an-amazon-mq-network-of-broker-topologies-for-distributed-microservices/) where they look at ActiveMQ topologies that customers can evaluate when planning hybrid deployment architectures spanning AWS Regions and customer data centers, using a network of brokers.

![arch](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2021/12/08/mq5-1024x478.png)

**Other posts worth checking out**

* [Achieve 35% faster training with Hugging Face Deep Learning Containers on Amazon SageMaker](https://aws.amazon.com/blogs/security/using-aws-security-services-to-protect-against-detect-and-respond-to-the-log4j-vulnerability/) shows you how to pretrain an NLP model (ALBERT) on Amazon SageMaker by using Hugging Face Deep Learning Container (DLC) and transformers library.
* [Build custom Amazon SageMaker PyTorch models for real-time handwriting text recognition](https://aws.amazon.com/blogs/machine-learning/build-custom-amazon-sagemaker-pytorch-models-for-real-time-handwriting-text-recognition/) shares the processes, scripts, and best practices to develop a custom ML model in Amazon SageMaker that applies deep learning (DL) techniques based on the concept outlined in the paper "GNHK: A Dataset for English Handwriting in the Wild" to transcribe text in images of handwritten passages into strings 
* [Automate Container Anomaly Monitoring of Amazon Elastic Kubernetes Service Clusters with Amazon DevOps Guru](https://aws.amazon.com/blogs/devops/automate-container-anomaly-monitoring-of-amazon-elastic-kubernetes-service-clusters-with-amazon-devops-guru/)  read on to find out about new features in Amazon DevOps Guru to help simplify and expand the capabilities of the operator to address some of the challenges due to the increasing number of abstractions and supporting infrastructure when implementing observability.
* [Proactive autoscaling of Kubernetes workloads with KEDA using metrics ingested into Amazon Managed Service for Prometheus](https://aws.amazon.com/blogs/mt/proactive-autoscaling-kubernetes-workloads-keda-metrics-ingested-into-aws-amp/) shows you how you can use Kubernetes based Event Driven Autoscaler (KEDA) to autoscale Amazon EKS Pods by querying the metrics stored in Amazon Managed Service for Prometheus
* [Implementing custom domain names with ROSA](https://aws.amazon.com/blogs/containers/implementing-custom-domain-names-with-rosa/) explains how to  register a domain using AWS registered domains, create a Route 53 hosted zone, and configure the Red Hat OpenShift Service on AWS to make use of that custom domain.
* [Replicate your data from Amazon Aurora MySQL to Amazon ElastiCache for Redis using AWS DMS](https://aws.amazon.com/blogs/database/replicate-your-data-from-amazon-aurora-mysql-to-amazon-elasticache-for-redis-using-aws-dms/) explores use cases and best practices when migrating data to an ElastiCache for Redis cluster.
* [How to fix SSH issues on EC2 Linux instances using AWS Systems Manager](https://aws.amazon.com/blogs/mt/how-to-fix-ssh-issues-on-ec2-linux-instances-using-aws-systems-manager/) shows you how you can use a feature of AWS Systems Manager to tackle unreachable Linux instances,  and fix common issues, such as OpenSSH file permissions, or gather system (OS) logs for analysis and troubleshooting
* [Cost savings by customizing metrics sent by Container Insights in Amazon EKS](https://aws.amazon.com/blogs/containers/cost-savings-by-customizing-metrics-sent-by-container-insights-in-amazon-eks/) is a post that shares how to configure the ADOT Collector for an Amazon EKS cluster

### Quick updates

**Spring Boot**

[v2.3.3](https://github.com/awspring/spring-cloud-aws/releases/tag/v2.3.3) is now available, and this version bumps a spring-messaging dependency to 5.3.13. Previous Spring Cloud AWS versions relied on spring-messaging that suffered from a security vulnerability (#206). If you relied on Spring Cloud AWS to determine spring-messaging version, please update to Spring Cloud AWS 2.3.3. Other changes include:

* Fix: context order when loading properties (Parameter Store and Secrets Manager) - @WtfJoke
* Docs: Mention no Aurora support in RDS docs (RDS) - @aravindparappil46
* Dependency Upgrade: Upgrade Maven Wrapper - @tinexw
* Enhancement: Log exception on message processing failure (SQS) - @ebussieres
* Dependency Upgrade: Upgrade Spring Cloud Build to 3.0.5 - @maciejwalkowiak
* Dependency Upgrade: Upgrade AWS SDK to 1.12.129 - @maciejwalkowiak

### Videos of the week

**RoboCat**

Loved this video, and now have ideas of how I can use my DeepRacer to do something similar. Searching for a humane way to scare mice out of his kitchen, Martin Paradesi modified an autonomous DeepRacer model car, and its open source code, to come up with a RoboCat that could scare mice away in the dark. Find out how his young sons contributed to the project.

{{< youtube H_lRlI6DnVg >}}

### Events for your diary

Watch this space for events in 2022. If you have an event you want me to publish here, please contact me and I will include it in this listing.

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)
