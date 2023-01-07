# refactored-waddle
Google Certified Associate Cloud Engineer Revision notes
[AWS Equivalents are in square brackets]


RDBMS
====
Cloud Spanner [Aurora] Distributed Structured Data. Does not support Point in time recovery!
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
Standard - used frequently
Nearline [IA] - used monthly
ColdLine [Glacier] - used quarterly
Archive [Glacier deep frozen] - used yearly

SNCA

Uniform or Fine Grained policies can be applied across the bucket. Fine Grained apply to one or move objects, uniform apply to everything in the bucket.

Storage Object Creator has no view or delete
Storage Object Admin has no access to manage buckets
Storage Admin - full access.

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

VPC
=====

VPC Flow logs

Shared VPC - Org can conect projects, resources, resources in other VPCs. 
           - Host or service project host.
           - 1 or more shared VPCs project attached to 1 project
Subnets can be expanded.

Cloud App  - HTTP, e.g. python. [Elastic Beanstalk ?]
Cloud Functions - [lambda]
Cloud Run - Container lamba [fargate]

## 4 Types Cloud Audit Logs
=========================
Admin Act
Data Act
System Event
Policy Denials

Monitoing Services -> Operation Suite

## Deployment Manager  - [CloudFormation]. YAML/Python/Jinja

After you have written a configuration file, you can preview the configuration before you create a deployment. Previewing a configuration lets you see the resources that Deployment Manager would create but does not actually instantiate any actual resources. The Deployment Manager service previews the configuration by:

Expanding the full configuration, including any templates.
Creating a deployment and “shell” resources.
You can preview your configuration by using the --preview query parameter.

## BIG DATA
========
Cloud Data Proc             Managed Hadoop/Map Reduce/Spark/Pig/Hive
Cloud Data Flow             Serverless Stream and Batch Processing
Big Query                   Data Warehouse
Pub/Sub                     MSK equivalent/SQS
Cloud Data Lab              Explorer data with Python/SQL

Lifecycle Actions
=================

1: Delete  - uses object versioning. 
2: Set Storage Class - based on age/created before/custom time before etc.

Managed Instance Groups [ASG]
=======================
Managed instance group template. Used to scale out.
Cloud Monitoring agent can be installed on instances.
VPC Flow logs.
Autohealing set to healthy (HTTP)
min_idle_instances can be used to set the size of the MIG

Shared VPC
==========
Orgs can connect projects/resources/services in other VPCS.
Host or service proejcts
Host: 1 or more shared VPCs 
Project attached to just project?

Loading BIG Data
================
Avro
CSV
JSON
ORC?
Parquet
Firestore exports in Cloud Storage

Google Cloud Adoption Framework is a document describing Google's cloud philosphy for C suites/Engineers before they decide to use Google Cloud.

VPN
===

Customer Gateway-> VPN Cloud Gateway -> Customer/Peer Gateway

Compute Instance Types
======================

N2 - balanced price/performance
M2 - High Memory
E2 - Cost
A2 - Accelerated GPU

Pre-emptible VMS are spot instances
 Require each member of the team to generate a new SSH key pair and to add the public key to their respective Google account. Then grant the compute.osAdminLogin role to the corresponding Google group of the operations team.



IAM
====
Principle of least privilege and multiple roles - always use predefined roles where possible
Member accounts are associated with Google Accounts.


Organisations
=============
Organisation Policies can be created by the *organisation policy administrator*

Organisation hierarchy
Org -> Folders -> Resources
One central billing account - Google Cloud Organisation
Resources - move project to the Organisation
Billing Export goes to Bigtable so can be queried using SQL.
Moving distribtued projects into one billing project - In the GCP Console, navigate to the Resource Manage section and move all projects to the root Organization. Can then setup a billing account to manage the underlying accounts.
Project Owner can delete project - doesn't need Organisation admin

Cloud Audit Logs
================
All Admin Activity is recoreded.
roles/logging.privateLogViewer is the minimum account for viewing these logs.
