---
title : "Introduction"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---
#### Overview
This is series about Serverless. To start, let's learn about what Serverless is, and what AWS Lambda is. Serverless is one of the cloud application development models. 
Cloud provides users with 4 development models as follows:
- IaaS (Infrastructure as a Service)
- PaaS (Platform as a Service)
- CaaS (Container as a Service)
- FaaS (Function as a Service)
![CloudComputingServicesModel](/images/1-Introduce.png?featherlight=false&width=90pc)

**Infrastructure as a Service**

This is the most common model when using the cloud, you may have used it every day without noticing. In this model, Cloud developers will expose APIs that interact with the underlying virtualized platform, such as APIs that interact with virtual machines, and APIs that interact with storage, ... to be able to create and manage infrastructure on Cloud. For example, AWS Cloud exposes EC2-related APIs, allowing you to easily create and manage EC2 ourselves using the Web Console or AWS CLI. In this model, you will create and manage your infrastructure and expansion.

**Platform as a Service**

This is a development model where the cloud will provide you with a Platform Framework for faster application development. For example, to deploy a web application in the cloud, you first need to create EC2 (virtual machine), then configure the security group so that traffic can go into EC2, then deploy the application on EC2, and many settings. So cloud developers provide platforms to do it faster. For example, AWS has AWS Elastic Beanstalk, which is a Platform that allows users to easily deploy a web application, with just a few simple mouse clicks on the Web Console to get a web application.

**Software as a Service**

This model is simply developing a container-based application and has a tool to manage our containers, such as Kubernetes. AWS offers AWS EKS for developing applications on the CaaS model.

**Function as a Service**

Finally and at the lowest level, the cloud allows users to develop applications based only on Functions, without the need to create and manage complex infrastructure, just manage functions. These functions are automatically scaled without any configuration, which is a key component of our Serverless model.

So Serverless is a model of developing applications and services without caring about the server. A Serverless application does not need to care about operating system resource allocation and management and ignores upgrade and security issues.

**Benefits of Serverless**
- No need to manage servers: You don't need to provision or maintain any servers. No software or runtime required to install, upgrade or administer.
- Scalable flexibility and high availability: FaaS will automatically scale according to traffic, without much configuration, unless the user wants it to scale in a certain way.
- Cost savings: You will only need to pay for each triggered function, pay as much as you use.
- Support many different languages: can use many different languages to write FaaS

**Disadvantages of Serverless**
- Hard to debug.
- Cold starts: takes a while if the function is triggered for the first time, or the function is rarely requested, then it takes a long time to run again.
- Difficult to organize source code: because each function will be deployed separately, the way to organize source code will be difficult or easy depending on different languages.
- Difficult to design a local dev environment.

#### AWS Lambda
AWS Lambda is an AWS service that allows you to run and manage functions. This is the main component of the Serverless model. In addition to AWS Lambda, AWS also provides us with the following services to build a Serverless model:
- S3 we use to save images
- API gateway for us to build REST API
- DynamoDB for databases
- Cognito for user authentication
- SQS used for queues
- SNS for notifications

AWS Lambda is designed for event-driven architecture, our code will be triggered based on an event, for example a client request to an API, all triggering processes are independent of each other and only pay per times the function is triggered and run. Compared to EC2, we have to pay by the hour, even if our code on EC2 does not process any requests for the user, we still have to pay, and Lambda does not.