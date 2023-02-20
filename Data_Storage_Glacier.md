# AWS Solutions Architect Associate: Data Storage Services - Glacier
Reference: https://docs.aws.amazon.com/amazonglacier/latest/dev/introduction.html
## Overview
- Archival data storage
- Fractions of a penny per GB/month
- 3 Access Methods
    - Expedited (3-5 min)
    - Standard (3-5 hours)
    - Bulk (5-12 hours)
- Admins define the region for data storage
- Automatically stored with AES 256-bit encryption
- A single AWS account can create upto 1,000 vaults per Region
- Only Empty vaults can be deleted
- Glacier support multipart uploads of archives, so a large archive is not required to be uploaded in a single action. 

## Glacier Integration
- S3 cold data can be moved to into Glacier automatically through lifecycle management
- Snow devices can be used to import data
- Storage Gateway can connect to Glacier

## Glacier Concepts
- Archives: Data that are inactive/cold.
- Vaults: The container to store archives.
- Vault Locks: Secures your vault and prevent unecessary retrieval costs. 
- Data Retrieval: Important to understand how to plan data retrieval
        - Up to 5% retrieved at no charge, no rollover. 
        - Vault can be configured to limit cost, by assigning a 'vault admin' 

## Glacier Operations
- Create vault, by selecting region and configuring a vault name.
- Set data retieval settings:
    - Free tier only (5%)
    - Max Retrieval Rate, set maximum GBs/ hour data retrieved 
    - No Retrieval Limit
- Event Notifications, set when Simple Notification Service (SNS) when a vault is accessed, etc.
    - You can create new SNS topics or integrate with exisiting SNS
- Set permission to who can access the vault
- Create Vault Lock policies
- Set tags


# Tape Gateway 
- Used with systems that only allow for backing up to tapes.
- Can be configured as punlic or private (VPC)
- A Virtual Tape Library (VTL) is a library of backup tapes that are actually just objects stored in an S3 bucket
