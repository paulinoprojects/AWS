# AWS Solutions Architect Associate: Data Storage Services - Elastic Block Storage
Reference: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AmazonEBS.html
## Overview 
- Elastic Block Storage (EBS) is used for persistent storage with EC2 instances and best practice to keep in the same AZ.
- EBS volumes cab be created and attached during the creation of an EC2 instance.
- EBS can be used for block-level storage from one AWS service to antoher.
- Use the AWS Console to create EBS volumes directly by selecting ELASTIC BLOCK STORE, Volumes 

## EBS Volume Types
- Magentic (Hard Drive)
- Solid State Drive (SSD)
  - General Purpose:
  - Provisioned IOPS (PIOPS): Provisioned input/output operation per seconds, gaurenteed performance
  - EBS-optimized instance should be used

 ## Protecting EBS Data
 - Snapshots
 - Volume Recovery
    - Attaching volumes from one instance to another
 - Encryption methods

# AWS Solutions Architect Associate: Data Storage Services - Elastic File System
Reference: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AmazonEFS.html

## Overview
- EFS is like NAS storage within the cloud for the cloud.
- EFS is free to be accessed by manay different instances, whereas the EBS is bound to an instance.
- EFS is sharable, meaning multiple instances can be use this simueltenously.
- Hierarchical, its a file storage location. Unlike prefix/delimiters in S3.
- Can be accessed through NFSv4 (Network File System)
- EFS is not supported on Windows instances, only Linux instances.

## Creating/Settings for EFS
1. Create EFS to a VPC (Virtual Private Cloud). Instances connect to a file system by using a network interface called a mount target.
    - Each mount target has an IP, which is automatically assined or can be specified.
2. Create mount targets, best practice to create mount target in each of your VPC's AZ so that EC2 instance across your VPC can access the file system
3. Configure performance mode:
    - General Purpose
    - Max I/O: optimized for appications where tens, hundreds, thousands of EC2 instances are accessing the file system, scales to higher level of aggregate throughput and operations per second with a tradeoff slightly latencies for file operations  

# Storage Comparison
 
![Storage Comparison](https://user-images.githubusercontent.com/111991325/219998040-afb38f09-7ba7-4fc9-8a97-30ba6a08a6b9.png)
