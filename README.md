﻿**Shared Responsibilities**

AWS Shared Responsibility Model => **Security of the Cloud**

S3, DynamoDB, RDS

Customer Responsibility => **Security in the Cloud**

Firewall & N/W configuration, IAM, Encryption

Shared Controls:

Patch Management, Configuration Management, Awareness & Training

Responsibilities in RDS:

**AWS:**

Manage underlying EC2, disable SSH access

Automated DB & OS patching

Audit underlying instance & disks & guarantee it functions

**Customer Responsibility:**

Ports / IP / SG inbound rules

In-database user creation & permissions

Public access for databases

Parameter groups or DB is configured to only allow SSL connections

DB encryption

Responsibilities in S3:

AWS:

Unlimited storage

Guarantee you get encryption

Ensure separation of the data between different customers

Ensure AWS employees can’t access your data

Customer Responsibility:

Bucket configuration

Bucket Policy

IAM user & roles

Enabling Encryption


**DDOS Attack (Distributed Denial of Service)**

![A diagram of a program

AI-generated content may be incorrect.](image1.png)

Normal users can’t access as many bots are requesting our application server

**AWS protects DDOS Attacks**

AWS Shield Standard (Free)

AWS Shield Advanced (Premium)

AWS WAF (Filter requests based on rules)

CloudFront & Route53 (Protection using global edge N/W)

AWS Auto Scaling

**WAF => Web Application Firewall**

![A diagram of a security system

AI-generated content may be incorrect.](image2.png)

AWS Shield Standard: Provides from attacks such as SYN/UDP floods, Reflection attacks & other layer3 / layer4 (TCP) attacks

AWS Shield Advanced: Amazon EC2, ELB, Amazon CloudFront, AWS Global Accelerator, Route53

AWS WAF: Protects from layer7 attacks (HTTP), it is deployed on ALB, API Gateway, CloudFront

Web ACL (Web Access Control List): Rules can include IP addresses, HTTP headers, HTTP body, or URI strings

Protects from SQL Injections, Cross-Site Scripting (XSS), Geo-match (block specific countries), Rate-based rules (to count occurrences of events)

**AWS N/W Firewall:**

Protect entire Amazon VPC

From layer3 to layer7 protection

VPC to VPC traffic, Outbound to internet, Inbound from internet, To/from Direct Connect & Site-to-Site VPN

**Note:** 

N/W ACL => Subnet Level

N/W Firewall => VPC level

![A diagram of a network firewall

AI-generated content may be incorrect.](image3.png)

**AWS Firewall Manager:**

Manages security rules in all accounts of an AWS Organization

**Amazon GuardDuty:**

Intelligent Threat discovery to protect your AWS Account

Uses ML algos, anomaly detection, 3<sup>rd</sup> party data

Protects against Crypto Currency attacks

![](image4.png)

**Amazon Inspector:**

Automated Security Assessments

Reporting & integration with AWS Security Hub

Send findings to Amazon Event Bridge

![A diagram of a company

AI-generated content may be incorrect.](image5.png)

**Inspector only for EC2, Container Images, Lambda funxctions**

**AWS Config Overview:**

Record configurations & changes over time

Storing configuration data into S3 (analysed by Athena)

Receive alerts (SNS notifications) for any changes

Per-region service

Can be aggregated across regions & accounts

View CloudTrail API calls if enabled

**Amazon Macie**

Data security and data privacy service that uses ML & Pattern matching too discover and protect your sensitive data in AWS

Macie helps identify and alert you to sensitive data, such as PII data

Notifies Event Bridge to do some integrations 

**AWS Security Hub Overview:**

Manage Security across AWS accounts and automate security checks

Must first enable AWS Config Service

![A diagram of a multi account

AI-generated content may be incorrect.](image6.png)

**Amazon Detective Overview:**

Finds root cause of security issues using ML & graphs

Automatically collects & processes events from VPC flow logs, CloudTrail, GuardDuty

**Root User Privileges:**

Root User = Account Owner

Has complete access

**Lock away** your AWS account root user **access Keys**

Change account settings

Close your AWS account

Register as a seller in the Reserved Instance Marketplace

**IAM Access Analyzer:**

Find out which resources are shared externally

Zone of trust = AWS Account or AWS Organization

Access outside zone of trusts = findings

**Amazon Rekognition:**

For faces, objects, etc from Images/Videos

**Amazon Transcribe:**

Convert speech to text

ASR (Automatic Speech Recognition)

Automatically remove PII data using **Redaction**

Automatic Language Identification for multi-lingual audio

Use cases: Customer service calls transcribe, closed captioning & subtitling, generate metadata for media assets

**Polly Overview:**

Text to speech

Create applications that talk

**Translate Overview:**

Natural & accurate language translation

**Lex + Connect Overview:**

Amazon Lex => tech that powers Alexa

ASR to convert speech to text

Helps build chatbots, call center bots

Amazon Connect:

Receives calls, create **contact flows**, cloud based **virtual contact center**

Can integrate with other CRM systems or AWS

![](image7.png)

**Comprehend Overview:**

For NLP

Fully managed & serverless service

Language of the text, sentiment analysis, POS & tokenization, organizes a collection of text files

Analyze customer interactions/emails

Create & group articles by topics

**SageMaker Overview:**

Fully managed service for developers / data scientists to build ML models

**Kendra Overview:**

Document search service (Search Engine)

Extract answers from within a document

**Amazon Personalize:**

For real-time personalized recommendations

Retail stores, media & entertainment

**Textract Overview:**

Extracts text, handwriting, and data from any scanned docs using AI & ML

Extracts data from forms & tables

Read & Process any type of document (PDFs, images…)

Use cases: Financial Services, Healthcare, Public Sector

**AWS Organizations Units (OUs)**

Global Service

Multiple AWS accounts can be managed

Consolidated Billing, pricing benefits, pooling of reserved EC2 instances

API available to automate AWS account creation

Restrict account privileges using **Service Control Policies (SCP)**

Multi Account vs One Account Multi VPC

Tagging Standards for billing purposes

Enable CloudTrail on all accounts, send logs to central S3 account

Send CloudWatch logs to central logging account

SCPs doesn’t apply to the master account

SCPs applied to all Users & Roles of the Account including Root

SCP doesn’t affect service-linked roles

SCP must have an explicit Allow (doesn’t allow anything by default)

Restrict access to certain services

Explicitly disable services

**Control Tower** => to setup multiple accounts

**AWS RAM (Resource Access Manager)**

Share AWS resources that you own with other AWS accounts

Share with any account or within your organisation

Avoid resource duplication

Aurora, VPC Subnets, Transit Gateway, Route 53, EC2 Dedicated Hosts, License Manager Configurations… all support RAM

**AWS Service Catalog:**

Self service portal to launch a set of authorized products pre-defined by admins

Includes: VMs, DBs, storage options, etc

Enter AWS Service Catalog!

Service Catalog Diagram

![A diagram of a product

AI-generated content may be incorrect.](image8.png)

**Pricing Models in AWS:**

1) Pay as you go
1) Save when you reserve
1) Pay less by using more
1) Pay less as AWS grows

**Free Services & Free Tier in AWS**

IAM, VPC, Consolidated Billing, Elastic Beanstalk, CloudFormation, Auto Scaling Groups

Free tier: EC2 t2.micro instance for a year, S3, EBS, ELB, AWS Data transfer

**Compute Pricing EC2**

Only charged for what you use

Number of instances

Instance Configuration

ELB running time & amount of data processed

Detailed monitoring

EC2:

1) On-demand instances
1) Reserved instances (1-3 years commitment)
1) Spot instances
1) Dedicated Host
1) Savings plans

Lambda & ECS:

Lambda: Pay per call, Pay per duration

ECS: EC2 Launch Type => No additional fees, you pay for AWS resources 

`		`Fargate=> Pay for vCPU & memory resources allocated to your applications in your containers

S3:

Storage class

Number & size of objects

Number & type of requests

Data transfer out of S3 region

S3 Transfer acceleration

Lifecycle transitions

Similar Service: EFS (pay per use)

EBS:

Volume type

Storage volume in GB per month provisioned

IOPS: General Purpose, Provisioned IOPS SSD, Magnetic

Snapshots

Data transfer: Outbound data transfer are tiered for volume discounts, Inbound is free

RDS:

Per hour billing

Database characteristics

Purchase type

Backup Storage: No additional charge for backup storage up to 100% of your total DB storage for a region

Additional Storage

No of input & output requests per month

Deployment types (single or multi AZs)

Data transfer (Outbound data transfer are tiered for volume discounts), Inbound is free

CloudFront:

Different geographic regions

Aggregated for each edge location

Data transfer out

No of HTTP/HTTPS requests

**Networking Costs in AWS per GB:**

![A diagram of a network

AI-generated content may be incorrect.](image9.png)

Use Private IP instead of public IP for good savings & better N/W performance

Use same AZ for max savings (at the cost of high availability)

**Savings Plan Overview:**

Commit a certain amount per hour for 1 or 3 years

**EC2 Savings Plan:**

Commit to usage of individual instance families in a region

All upfront, partial upfront, no upfront

**Compute Savings Plan:**

Regardless of family, region, size, OS, tenancy, compute options

EC2, Fargate, Lambda

**Machine Learning Savings Plan:**

SageMaker

**AWS Compute Optimizer Overview:**

Reduce costs & improve performance by recommending optimal AWS resources

Uses ML to analyze your resources configs & their utilization CloudWatch metrics

Supported resources:

EC2 instances, EC2 ASGs, EBS Volumes, Lambda functions

Recommendations can be exported to S3

**Billing & Costing Tools:**

1) Estimating costs in the cloud: Pricing calculator
1) Tracking costs in the cloud: Billing dashboard, cost allocation tags, cost & usage reports, cost explorer
1) Monitoring against costs plans: billing alarms, budgets

**Pricing Calculator:**

Estimate cost for your solution architecture

**AWS Billing Dashboard**

Cost breakdown by month by service by region by account, etc

**Cost Allocation Tags:**

To track your AWS costs on a detailed level

AWS generated tags: automatically applied to resource you create (**aws:** createdBy)

User generated tags: Defined by the user (**user:**)

**Tagging & Resource Groups:**

Tags => used for organizing resources

EC2: instances, images, load balancers, security groups

RDS, VPC resources, Route 53, IAM users

Resources created by CloudFormation are all tagged the same way

Free naming, common tags are: **Name, Environment, Team**

Tags can be used to create **Resource groups**

Create, maintain, and view a collection of resources that share common tags

Manage these tags using the Tag Editor

**Cost & Usage Reports:**

Dive deeper into your AWS costs & usage

The AWS cost & usage report contains the most comprehensive set of AWS cost & usage data available, including additional metadata about AWS services, pricing & reservations (eg. Amazon EC2 Reserved Instances (RIs))

Can be integrated with Athena, Redshift or QuickSight

**Cost Explorer:**

Forecast usage up to 12 months based on previous usage

Visualize, understand and manage your AWS costs & usage over time

Analyze data at high level

Monthly, Hourly, Resource level granularity

Choose an optimal Savings Plan

**Billing Alarms in CloudWatch**

Stored in CloudWatch us-east-1

For overall worldwide AWS costs

For actual cost, not for projected costs

Intended a simple alarm (not as powerful as AWS Budgets)

**AWS Budgets:**

Create budget & send alarms when cost exceeds the budget

4 types: Usage, Cost, Reservation, Savings Plan

For Reserved Instance (RI): Track utilization, Supports EC2, ElastiCache, RDS, RedShift

Up to 5 SNS notifications per budget

Can filter by: Service, Linked Account Tag, Purchase Option, Instance Type, Region, AZ, API Operation, etc

Same options as AWS Cost Explorer!

**AWS Cost Anomaly Detection:**

Continuously monitor your cost & usage using ML to detect unusual spends

Sends you anomaly detection report with RCA (root cause analysis)

Can notify you in case of anomalies

**AWS Service Quotas:**

Notify you when you’re close to a service quota value threshold

Create CloudWatch Alarms on the Service Quotas console

Eg: Lambda concurrent executions

Request a quota increase from AWS Service Quota or shutdown resources before limit is reached

**AWS Trusted Advisor:**

High level AWS account assessment

6 Categories:

Cost optimization, Performance, Security, Fault tolerance, Service limits, Operational Excellence

Security checks alone are free, others are paid

Business & Enterprise Support plan:

Full set of checks

Programmatic Access using **AWS Support API**

**Support Plans for AWS**

Basic Support: free

4 types: Developer, Business, Enterprise On-Ramp, Enterprise

Basic: 24x7 access to customer service alone, access to 7 core trusted advisor checks, Personal health dashboard

Developer: Basic + Business hours email address, Unlimited cases/contacts, within 12 business hours

Business: if you have production workloads, Trusted Advisor: Full set of checks + API access, 24x7 phone, email & chat access, Unlimited cases/contacts, access to Infrastructure Event Management for additional fee, if prod system impaired < 4 hours, if prod system down < 1 hour

On-Ramp: Business + Pool of TAM (Technical Account Managers), Concierge Support team, Infrastructure Event Management, Well Architected & Operations Reviews,Case severity/ response times: prod impaired < 4 hours, prod system down < 1hour, Business critical system down < 30 minutes

Enterprise: On-Ramp + designated TAM, AWS Incident Detection & Response, Business critical system down < 15 minutes

**Account Best Practices:**

AWS Organizations

SCP (Service Control Polices)

AWS Control Tower

Use Tags & Cost Allocation Tags

IAM guidelines

Config to record all resources configurations

CloudFormation to deploy stacks across accounts & regions

Trusted Advisor to get insights, Support Plan

Send Service logs & Access logs to S3 or CloudWatch logs

CloudTrail to record API calls

AWS Service Catalog for predefined stacks defined by Admin

**Billing Summary:**

Compute Optimizer

Pricing Calculator

Billing Dashboard

Cost Allocation tags

Cost & Usage Reports

Cost Explorer

Billing Alarms

Budgets

Savings Plans

Cost Anomaly detection

Service Quotas
