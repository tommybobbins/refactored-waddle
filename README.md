# refactored-waddle
Google Certified Associate Cloud Engineer Revision notes
[AWS Equivalents are in square brackets]


RDBMS
====
Cloud Spanner [Athena] Distributed Structured Data
Cloud SQL (MySQL , postgres)

NoSQL
=====
Bigtable [DynamoDB]
Firestore - noSQL for mobile web iot
Firebase store and sync data
Memorystore - Redis/Elasticache/Memcache

Pricing calculator
==================

Cloud Storage = [S3]
Cloud Filestore = [EFS]/NFS
Persistent Disk = [EBS]

Cloud Storage
=============
Normal
Nearline [IA]
ColdLine [Glacier]
Archive [Glacier deep frozen]

Uniform or Fine Grained policies can be applied across the bucket. Fine Grained apply to one or move objects, uniform apply to everything in the bucket.

RetentionPolicy
===============
Bucket Locking - in line with data retention policies
Object lifecycle management - TTL for objects, move storage classes.

Lifecycle actions
1: Delete.

2: Set Storage Class based on something similar to :
   Age, Created Before, Custom time before etc.

Managed Instance groups - [ASG]
                        - Template, scale out and scale in.
Cloud Monitoring Agent  - [CloudWatch Agent]
VPC Flow logs

Shared VPC - Org can conect projects, resources, resources in other VPCs. 
           - Host or service project host.
           - 1 or more shared VPCs project attached to 1 project

Cloud App  - HTTP, e.g. python. [Elastic Beanstalk ?]
Cloud Functions - [lambda]
Cloud Run - Container lamba [fargate]

4 Types Cloud Audit Logs
=========================
Admin Act
Data Act
System Event
Policy Denials

Monitoing Services -> Operation Suite
Deployment Manager  - [CloudFormation]. YAML/Python/Jinja
