## EC2 intro

EC2 = traditional server/machine
e.g. nodejs server in the cloud

Different hardware and software options
Pricing is based on guaranteed availability

AMI = Amazon Machine Image
Software config for the image, e.g. OS
For dev, often use Ubuntu

Check "Free tier eligible"


## DocumentDB

Compatible with Mongo, but is not actually Mongo


## DynamoDB

Another NoSQL DB, but is Amazon's proprietary DB
Key-value store


## RDS

Relational Database Service (MySQL, Oracle, etc)
Aurora - Amazon proprietary DB that is MySQL & Postgres compatible. Mimics
speed and performance combined with open-source

RDS can get really expensive (storage, uptime, availability)!

Some networking will come up - important for RDS DBs to be in different zones
for availability

Instance class - speed/power/memory of the DB instance

Endpoint - is the instance URL for the backend to use to connect to the DB


## S3

Simple Storage Service
Used for storing static files
Very very cheap
Names of buckets are globally unique and cannot be changed after creation

Global service, but buckets exist in a region

S3 can be used to host a static web application - you'll need to enable public
access to the bucket (via a setting), and then allow access to the files in
the bucket by adding a bucket policy


### IAM

For the purposes of uploading a static file to S3, we create a specific user
for doing that to minimise the damage that could be caused if the default user
gets compromised and then floods the bucket with many files, causing billing
issues
This is done in IAM. Use the "Access key" AWS Credential type (this gives
access key and secret access key)

In a real world setting, programmatic users would be in their own group which
would have a relatively locked down set of settings

In AWS, you use policies to add permissions to users and groups. A policy is
a script that explains the level of access that the recipient has.


## Lambda

Serverless functions - run code without spinning up an entire EC2 instance
Don't need to worry about provisioning a server, configuring it, etc

Super cheap - a number of calls per month for free

Various ways to trigger these - e.g. run after a row is created in a DB
Common way for web devs is in response to a HTTP endpoint (but need the API
gateway service to do this)

API Gateway - create different endpoints and add things to them like routing,
auth, protection against spikes in traffic


## Other services

Route 53 - DNS provider (e.g. connect S3 to custom domain)
CloudFront - content delivery
CloudFormation - meta-service, infra-as-code, tells AWS how to provision
various other AWS services without you needing to manually click in the UI
Amplify - for building fullstack apps quickly


## Where to go next

Billing
Identity & Access Management (IAM) - groups, users, roles, security roles


## Certifications

Cloud Practitioner - basic level
