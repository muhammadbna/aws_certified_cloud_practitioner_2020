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
