**Shared Responsibilities**

AWS Shared Responsibility Model =\> **Security of the Cloud**

S3, DynamoDB, RDS

Customer Responsibility =\> **Security in the Cloud**

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

Ensure AWS employees can't access your data

Customer Responsibility:

Bucket configuration

Bucket Policy

IAM user & roles

Enabling Encryption

**DDOS Attack (Distributed Denial of Service)**

![A diagram of a program AI-generated content may be
incorrect.](./image1.png){width="6.268055555555556in"
height="3.2305555555555556in"}

Normal users can't access as many bots are requesting our application
server

**AWS protects DDOS Attacks**

AWS Shield Standard (Free)

AWS Shield Advanced (Premium)

AWS WAF (Filter requests based on rules)

CloudFront & Route53 (Protection using global edge N/W)

AWS Auto Scaling

**WAF =\> Web Application Firewall**

![A diagram of a security system AI-generated content may be
incorrect.](./image2.png){width="6.268055555555556in"
height="3.1951388888888888in"}

AWS Shield Standard: Provides from attacks such as SYN/UDP floods,
Reflection attacks & other layer3 / layer4 (TCP) attacks

AWS Shield Advanced: Amazon EC2, ELB, Amazon CloudFront, AWS Global
Accelerator, Route53

AWS WAF: Protects from layer7 attacks (HTTP), it is deployed on ALB, API
Gateway, CloudFront

Web ACL (Web Access Control List): Rules can include IP addresses, HTTP
headers, HTTP body, or URI strings

Protects from SQL Injections, Cross-Site Scripting (XSS), Geo-match
(block specific countries), Rate-based rules (to count occurrences of
events)

**AWS N/W Firewall:**

Protect entire Amazon VPC

From layer3 to layer7 protection

VPC to VPC traffic, Outbound to internet, Inbound from internet, To/from
Direct Connect & Site-to-Site VPN

**Note:**

N/W ACL =\> Subnet Level

N/W Firewall =\> VPC level

![A diagram of a network firewall AI-generated content may be
incorrect.](./image3.png){width="4.354774715660542in"
height="4.229757217847769in"}

**AWS Firewall Manager:**

Manages security rules in all accounts of an AWS Organization

**Amazon GuardDuty:**

Intelligent Threat discovery to protect your AWS Account

Uses ML algos, anomaly detection, 3^rd^ party data

Protects against Crypto Currency attacks

![](./image4.png){width="6.268055555555556in"
height="2.813888888888889in"}

**Amazon Inspector:**

Automated Security Assessments

Reporting & integration with AWS Security Hub

Send findings to Amazon Event Bridge

![A diagram of a company AI-generated content may be
incorrect.](./image5.png){width="4.083903105861768in"
height="4.354774715660542in"}

**Inspector only for EC2, Container Images, Lambda funxctions**

**AWS Config Overview:**

Record configurations & changes over time

Storing configuration data into S3 (analysed by Athena)

Receive alerts (SNS notifications) for any changes

Per-region service

Can be aggregated across regions & accounts

View CloudTrail API calls if enabled

**Amazon Macie**

Data security and data privacy service that uses ML & Pattern matching
too discover and protect your sensitive data in AWS

Macie helps identify and alert you to sensitive data, such as PII data

Notifies Event Bridge to do some integrations

**AWS Security Hub Overview:**

Manage Security across AWS accounts and automate security checks

Must first enable AWS Config Service

![A diagram of a multi account AI-generated content may be
incorrect.](./image6.png){width="6.268055555555556in"
height="2.767361111111111in"}

**Amazon Detective Overview:**

Finds root cause of security issues using ML & graphs

Automatically collects & processes events from VPC flow logs,
CloudTrail, GuardDuty

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
