# Overview

## History *(not in the exam)*
- Conceived in response to cloud computing
- 2003 Chris Pinkhan and Benjamin Black presents paper on what Amazon's internal infrastructure should look like
- Suggested sell it as a service
- 2004 SQS officially launched
- 2006 AWS officially launched
- 2007 180,000+ developers

## AWS Global Infrastructure
- Regions, Availability Zones (AZ) and Edge Locations (EL)
- 2017: 16 Regions, 44 AZs and 96 ELs
- For 2018: 6 Regions and 17 AZs
- Region: geographical area (London, Tokyo, Sydney), 2+ AZs
- AZ: 1+ discrete data centers, place to put resources with redundant power/networking/connectivity, housed in separated facilities
- EL: endpoints for caching content -> CloudFront: Amazon's CDN

## AWS Platform - Concepts and Components (take a look at AWS Console)
### Compute
#### EC2
- Elastic Compute Cloud
- Consists in VMs inside the AWS platform (physical as well)

#### EC2 Container Service
- Run and manage Docker container at scan_length

#### Elastic Beanstalk
- For devs who don't understand AWS and just want to upload and focus on code
- Provision load balancers, EC2, scaling groups

#### Lambda
- Code you upload into the cloud and then you control when it executes
- No worries about any underlying physical/virtual machines, worry about the code

#### LightSail
- Amazon Virtual Private Service (VPS)
- For people who don't want to understand AWS
- Provisions with:
  - Actual server
  - Fixed IP address
  - RDP/SSH for Windows/Linux
  - Management console
  - Version of EC2
  - Worry about underlying OS

### Batch
- Batch computing in the cloud

### Storage
#### S3
- One of oldest storage services
- Simple Storage Service
- Upload files into buckets that are in the cloud

#### EFS
- Elastic File System
- Network attached storage
- Typically store files on a EFS volume and mount it (share) on multiple VMs

#### Glacier
- For data archives
- Cheap

#### Snowball
- A way of bringing large amounts of data into AWS data centers
- Write data physically to a disk and then import it manually

#### Storage Gateways
- Virtual appliances
- VMs installed in your data center/office and they will replicate information back to a S3

### Databases
#### RDS
- Relational Database Service
- MySQl, MSSQL, Postgresql, Aurora, Oracle, any RDBS

#### DynamoDB
- Non relational database

#### Elasticache
- For caching commonly queried things from the database

#### Red Shift
- Data warehousing or business intelligence
- Complex queries

### Migration
#### AWS Migration Hub
- Tracking service for apps as you migrate them into AWS
- Integrates with other migration services

#### Application Discovery Service
- Tracks dependencies for applications

#### Database Migration Service
- Migrate databases into AWS

#### Server Migration Servers
- Helps migrate physical/virtual server into AWS cloud

#### Snowball *(from Storage)*
- Migrate large amounts of information into the cloud

### Networking & Content Delivery
#### VPC
- Amazon Virtual Private Cloud
- "Virtual data center"
- Need to configure:
  - Firewall
  - AZs
  - Address ranges
  - Route tables
  - ACLs
  - Etc.

#### CloudFront
- Amazon CDN
- Media assets which gets stored closer the users so they can access from that edge location

#### Route53
- Amazon DNS service
- Looks up for a name it's going to resolve with a IPv4 and IPv6 address

#### API Gateway
- Used when creating a *Serverless* website using **Polly**
- A way of creating your own APIs for your services to talk to

#### Direct Connect
- A way of running a dedicated line from your office/data-center directly to Amazon and directly to your VPC

### Developer Tools
#### CodeStar
- Getting a group of devs to work
- A way of project managing the code
- Continuous Delivery Tool chain

#### CodeCommit
- Store code
- Source control (private git repos)

#### CodeBuild
- Compile code and run tests against it
Produce software packages ready to deploy

#### CodeDeploy
- Deployment service
- Automates app deployment to EC2 instances as well to on premise instances and *lambda functions*

#### CodePipeline
- Continuous delivery service
- Model, visualize and automate the steps requires to release software

#### X-Ray
- Debug/Analyze service apps

#### Cloud9
- IDE environment
- Develop code inside the AWS console instead of your desktop

### Management Tools
#### CloudWatch
- Monitoring service

#### CloudFormation
- Scripting infrastructure
- It takes the OS installation and its configuration and turns it into code
- Take a cloud formation template and it can be deployed as a WordPress, Share Point, Joomla, etc.
- Code can be reused among regions

#### CloudTrail
- Every time an action (creating an S3 bucket, user, EC2 instance, etc) takes place inside the AWS Console, it triggers an API calls which logs it
- Turned on by default
- Stores records for one week

#### Config
-  Monitors configuration of entire AWS environment
- Has point in-time snapshots to move backwards and forwards  

#### OpsWorks
- Similar to Beanstalk but more robust
- Uses chef and puppet
- A way of automating your environments

#### Service Catalog
- To manage a catalog of IT services approved for use on AWS
- Can be from VM images, individual OS, databases, etc.

#### Systems Manager
- Interface for managing your AWS resources
- Typically used for EC2 (applying patches across a bunch EC2 instances)
- Grouping resources by different departments/applications

#### Trusted Advisor
- It will give advice across multiple disciplines (opened ports, AWS services use)

#### Managed Services
- No worries about EC2 instances or autoscaling then Managed Services can help with it

### Media Services
#### Elastic Transcoder
- Takes a video and resizes it to look good in any device

#### MediaConvert
- File based video transcoding service with broadcast features
- Allows create video on demand content for broadcast and multi-screen delivery at scale

#### MediaLive
- Broadcast live video processing service
- Creates high quality video streams to deliver to broadcast TVs and internet connected multi-screen devices

#### MediaPackage
- Protects and packages videos to be delivered over the Internet

#### MediaStore
- Media optimized storage service
- Great performance, consistency and low latency to deliver live and on demand video content

#### MediaTailor
- Allows to do targeting advertising into video streams without sacrificing broadcast level QoS

### Machine Learning
#### SageMaker
- Makes deep learning really easy for dev to use
- Around neural networks

#### Comprehend
- Makes sentimental analysis around data
- Can tell if people are saying good or bad things about something

#### DeepLens
- Artificially aware camera
- Camera itself can figure  out what is it's looking at without being connected to a AWS backend

#### Lex
- What power the Amazon's Alexa service
- Artificially intelligent way of chatting to customers

#### Machine Learning
- Different to deep learning *(Sage)*
- Data set is threw into the AWS cloud and then it will analyze that data and give some results it will detect and predict an outcome
- Amazon recommend products

#### Polly
- Takes text and turns it into speech
- choose from different languages, regions, accents

#### Rekognition
- Video and images, uploads a file to it and it will tell you what is in that file

#### Amazon Translate
- Amazon's version of Google Translate

#### Amazon Transcribe
- Automatic speech recognition
- Can upload video or mp3 files and it will take what it recognizes

### Analytics
#### Athena
- Allows to run SQL core queries against thins in your S3 buckets (spreadsheets, CSV files)
- Completely *Serverless*

#### EMR
- Elastic Map Reduce
- To process large amount of data
- For Big Data solutions

#### CloudSearch
#### ElasticSearch Service

#### Kinesis
- A way of ingesting large amounts of data into AWS (social media feeds, tweets, a hashtag)

#### Kinesis Video Streams
- Ingesting video from devices and run a whole bunch processing against it

#### QuickSight
- Amazon's business intelligence tool

#### Data Pipeline
- A way of moving data between different AWS services

#### Glue
- Used for ETL

### Security & Identity & Compliance
#### IAM
- Identity access management service

#### Cognito
- A way of doing device authentication
- Once user has authenticated (using facebook, linked, gmail, etc.) on mobile, it can use Cognito to request temporary access to AWS resources

#### GuardDuty
- Monitors for malicious activity in your AWS account

#### Inspector
- Agent installed on your VM or your EC2 instance
- Runs a bunch of tests against it to check for security vulnerabilities

#### Macie
- Will scan S3 buckets for things containing personally identifiable information (PII)

#### Certificate Manager
- A way of managing SSL certificates

#### CloudHSM
- Hardware Security Module
- Dedicated bits of hardware to store keys (private and public)
- Need theses keys to access EC2 instances
- Store other keys like encryption

#### Directory Service
- Integrating MS Active Directory with AWS

#### WAF
- Web Application Firewall
- Layer 7 firewall
- Stops CRSF and SQL injections
- Monitoring at application level what the user is doing

#### Shield
- Prevents DDoS

#### Artifact
- Portal for on-demand access to download AWS compliant reports and manage select agreements
- Allows you to download things like SOC (Service Organization Controls), PCI (Payment Card Industry) reports, etc.
- A way of downloading and inspecting Amazon's documentation

### Mobile Services
#### Mobile Hub
- Management console for mobile apps
- When having a mobile app just create a mobile hub and it will set up all the needed AWS services for you
- Generates a cloud configuration file
- Use the AWS mobile SDK to connect mobile app to new AWS backend

#### Pinpoint
- A way of using targeted push notifications to drive mobile engagement

#### AWS AppSync
- Updates the data in web and mobile applications in real time
- Also data for offline user as soon as they reconnect

#### Device Farm
- A way of testing your apps on real life devices (android/iphone/etc)

#### Mobile Analytics
- Analytic service for mobiles

### AR / VR
#### Sumerian
- First language ever written, with this in mind AWS is trying to say here is that once we started writing things down, we found a common set of tools use to communicate ideas
- Used for augmented reality, virtual reality and 3D application design
- Allows you to use a common set of tools to create these environments

### Application Integration
#### Steps Functions
- Managing different Lambda functions

#### Amazon MQ
- A way of doing message queueing

#### SNS
- Simple Notification Service

#### SQS
- Simple Queue Service
- A way of decoupling your infrastructure
- Typical case: if a EC2 instance is pulling messages from the queue and it dies, the message remains in the queue so another EC2 instance can pull it later

#### SWF
- Simple Workflow
- Amazon uses in warehouses every time you order a package online a workflow job gets created
- Can have human beings involved

### Customer Engagement
#### Connect
- Contact center as a service
- Like having you own call center in the cloud

#### Simple Email Service
- Great way of sending large amounts of emails, highly scalable, very cost effective, great deliverability and highly customizable

### Business Productivity
#### Alexa for Business
- Zoila

#### Chime
- Used for video conferencing (Zoom/Hangouts)

#### Work Docs
- Like a DropBox for AWS to safely and securely store work related documents

#### WorkMail
- Like Office 365, Amazon's version

### Desktop & App Streaming
#### Workspaces
- VDI solution
- Running actual OS inside the VMs and cloud streamed down into your device

#### AppStream 2.0
- A way of streaming live the actual applications to your devices

### Internet of Things
#### iOT
- Having thousands or millions of different devices sending information

#### iOT Device Management
- For managing this number of devices

#### Amazon FreeRTOS
- OS for microcontrollers, free

#### Greengrass
- Software that lets you run local compute messaging, data caching, sync and machine learning interface capabilities for connected devices in a secure way

### Game Development
#### GameLift
- Service to help you develop games
