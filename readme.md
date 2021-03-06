AWS Certified Cloud Practitioner Training 2020 notes

- [Cloud concepts: What is cloud computing?](#cloud-concepts-what-is-cloud-computing)
  - [Definition](#definition)
  - [On-premise v.s. cloud providers](#on-premise-vs-cloud-providers)
  - [Benefits of Cloud provider over on-premise?](#benefits-of-cloud-provider-over-on-premise)
  - [Types of cloud computing](#types-of-cloud-computing)
  - [Cloud computing deployment models](#cloud-computing-deployment-models)
- [AWS global infrastructure](#aws-global-infrastructure)
  - [Introduction](#introduction)
  - [Regions](#regions)
  - [Availability zones (AZs)](#availability-zones-azs)
  - [Edge locations](#edge-locations)
  - [GovCloud Regions (only for US)](#govcloud-regions-only-for-us)
- [Introduction to AWS tools](#introduction-to-aws-tools)
  - [Budgets](#budgets)
  - [Identity and Access Management (IAM)](#identity-and-access-management-iam)
  - [Elastic Compute Cloud (EC2)](#elastic-compute-cloud-ec2)
  - [Systems Manager Session Manager](#systems-manager-session-manager)
  - [Amazon Machine Images (AMI)](#amazon-machine-images-ami)
  - [Auto Scaling Groups](#auto-scaling-groups)
  - [Elastic Load Balancer](#elastic-load-balancer)
  - [Simple Storage Service (S3)](#simple-storage-service-s3)
  - [CloudFront](#cloudfront)
  - [Relational Database Service (RDS)](#relational-database-service-rds)
  - [Lambda](#lambda)
- [EC2 pricing models](#ec2-pricing-models)
  - [On-demand instances](#on-demand-instances)
  - [Reserved Instances (RI)](#reserved-instances-ri)
  - [Spot instances](#spot-instances)
  - [Dedicated instances](#dedicated-instances)

# Cloud concepts: What is cloud computing?

## Definition

The practice of using a network of remote servers hosted on the Internet to store, manage, and process data, rather than a local server or a personal computer

## On-premise v.s. cloud providers

| On-premise  | Cloud providers  |
|---|---|
| You own the servers   | Someone else owns the servers   |
| You hire the IT people   |  Someone else hires the IT people  |
| You pay or rent the real-estate  | Someone else pays or rents the real-estate  |
| You take all the risk  | You are responsible for configuring cloud services, and code, someone else takes care of everything else  |

## Benefits of Cloud provider over on-premise?

1. Trade capital expense for variable expense
   - No upfront-cost instead of paying for data centers and servers.
   - Pay on-demand when you consume computing resources
2. Benefit from massive economies of scale:
   - Usage from thousands of customers aggregated in the cloud.
   - Sharing the cost with other customers to get unbeatable savings
3. Stop guessing capacity:
   - Instead of paying for idle or underutilized servers, you can scale up or down to meet current need
4. Increase speed and agility:
   - Launch resources within a few clicks in minutes instead of waiting weeks for your IT team to implement the solution on-premise
5. **Stop spending money on running and maintaining data centers**:
    - Focus on customers, rather than the heavy lifting of racking, stacking and powering servers
6. Go global in minutes:
   - Deploy app in multiple regions around the world with a few clicks.
   - Provide lower latency and better experience for your customers.

## Types of cloud computing

1. Software as a Service (SaaS) for customers:
   - A completed product that is run and managed by the service provider.
   - Don't worry about how the services is maintained. It just works and remains available.
   - e.g. Gmail, SalesForce
2. Platform as a Service (PaaS) for developers:
   - No need to manage underlying infrastructure
   - Focus on deployment and management of your applications
   - Don't worry about provisioning, configuring or understanding the hardware or OS
   - e.g. Heroku, Netlify
3. Infrastructure as a Service (IaaS) for admins
   - Basic building blocks for cloud IT
   - Provides access to networking features, computers and data storage space
   - Don't worry about IT staff, data centers and hardware

## Cloud computing deployment models

1. Cloud: Fully utilizing cloud computing
   - Good for startups, SaaS offering, or new projects and companies
   - e.g. Dropbox, Squarespace
2. Hybrid: Using both cloud and on-premise
   - Good for organizations that provide large professional services, with legacy on-premises
   - e.g. Banks, Deloitte
3. On-premise: Deploying resources on-premises, using virtualization and resource management tools (a.k.a private cloud)
   - Public sectors e.g. government
   - Systems with super sensitive data e.g. hospitals
   - Large enterprise with heavy regulations e.g. insurance companies

# AWS global infrastructure

## Introduction

1. **Regions**: Physical location in the world with multiple Availability zones
2. **Availability zones (AZs)**: Data centers that is the infrastructure of the cloud
3. **Edge location**: Data center owned by a trusted partner of AWS

## Regions

- Geographically distinct location which has multiple data centers
- Each region is physically isolated from and independent of every other region in term of location, power and water supply
- Each region has at least 2 AZs (redundancy purposes)
- Not all services are available in all regions

## Availability zones (AZs)

- AZ is a data center owned and operated by AWS in which AWS services run
- AZs are represented by a region code, followed by a letter identifier e.g. us-east-1a
- Multi-AZ: distributing your instances across multiple AZs allows failover configuration for handling requests when one goes down
- < 10ms latency between AZs

## Edge locations

- Data center owned by a trusted partner of AWS which has a direct connection to the AWS network
- These locations serve requests for "CloudFront" and "Route 53" going to either of these services will be routed to the nearest edge location automatically
- "S3 Transfer Acceleration" traffic and "API Gateway" endpoint traffic also uses the AWS Edge Network
- Allows for low latency no matter where the end use is geographically located

## GovCloud Regions (only for US)

- Allow customers to host sensitive Controlled Unclassified Information nd other types of regulated workloads
- Only operated by employees who are US citizens on US soil
- Only accessible to US entities and root account holders who pass a screening process
- Customers can architect secure cloud solutions that comply with US regulations

# Introduction to AWS tools

## Budgets

- Create custom budgets that alert you when you exceed (or are forecasted to exceed) the thresholds that you set

## Identity and Access Management (IAM)

- Control who is authenticated (signed in) and authorized (has permissions) to use resources
- When creating an AWS account, you have complete access to all AWS services and resources in the account (i.e. root user). This root user should not be used for everyday tasks, even administrative ones. Only use the root user to create your first IAM user, and then securely lock away the root user credentials and use them to perform only a few account and service management tasks

## Elastic Compute Cloud (EC2)

- Essentially a server that is provisioned to run your application in

## Systems Manager Session Manager

- Provide an interface to access your EC2 servers through a browser-based shell on AWS platform or through the AWS Command Line Interface (CLI)
- Provides secure and auditable instance management without opening inbound ports or managing SSH keys

## Amazon Machine Images (AMI)

- Create a "template" of your EC2 server so that it can be reused
- Includes server and security configurations

## Auto Scaling Groups

- Handles availability of your EC2 server (ensure that 1 EC2 server is at least running)
- Allow configuration to flexibly increase and decrease EC2 instances to match traffic demands

## Elastic Load Balancer

- Able to distribute traffic evenly to multiple EC2 instances
- If an EC2 instance is unhealthy, the traffic will then be routed to a healthy EC2 instance

## Simple Storage Service (S3)

- Essentially Dropbox, or a Google Drive

## CloudFront

- Used as a Content Distribution Network (CDN). To allow users from around the world to access your content in your S3 quickly (low latency, and high transfer speeds)
- The contents to be served will be distributed to servers across the world

## Relational Database Service (RDS)

- Able to provision different database products (e.g. MySQL, PostgreSQL) for your application

## Lambda

- Run code without setting up or managing an application/server

# EC2 pricing models

## On-demand instances

- No up-front payment and no long-term commitment
- Charged by the hour or by the minute
- Suitable for applications where the workload is short-term, spike-y or unpredictable. When you have a new app for development or you want to run experiments

## Reserved Instances (RI)

- For applications that have a steady-state, predictable usage, or require reserved capacity
- Pricing is based on `Term x Class Offering x Payment Option`
- Terms: Commit to a 1 year or 3 year contract. The longer the term the greater, the savings
- Payment options: "All Upfront", "Partial Upfront" and "No Upfront". The greater upfront, the greater the savings
- RIs can be shared between multiple accounts within an organizations
- Unused RIs can be sold in the "Reserved Instance Marketplace"

## Spot instances

- AWS has unused compute capacity that they want to maximize the utility of their idle servers
- Spot instances provide a discount of 90% compare to On-Demand pricing.
- Spot instances can be terminated if the computing capacity is needed by on-demand customers
- Designed for applications that have flexible start and end times or applications that are only feasible at very low compute costs
- Termination considerations
  - Instances can be terminated by AWS at anytime
  - If your instance is terminated by AWS, you don't get charged for a partial hour of usage
  - If you terminate an instance, you will be charge for any hour that it ran

## Dedicated instances

- Designed to meet regulatory requirements. When you have strict server-bound licensing that won't support multi-tenancy or cloud deployments
- Enterprises and large organizations may have security concerns or obligations about against sharing the same hardware with other AWS customers
- Multi-tenant
  - When multiple customers are running workloads on the same hardware. **Virtual isolation** is what separate customers
  - e.g. rent out room(s) in a house
- Single tenant
  - When a single customer has dedicated hardware. **Physical isolation** is what separate customers
  - e.g. rent out a house
