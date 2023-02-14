
# AWS Solutions Architect Associate: Data Storage Services
## Design Considertions for Storage Services
- Size
  - What types of data are you storing?
  - Storage size requirements? -GB, -TB -PB?
- Performance
  - How accessable do you need your data?
- Cost
  - Find the balance between performance, security, and operational cost.

### Types of Storage Services
- Simple Sotrage Service (S3)
- Glacier
- CloudFront
- Elastic Block Storae (EBS)
- Storage Gateway
- Snow Family
- Databases

### Block Storage
- Refers to a type of storage that is used to store individual blocks of data, rather than files. Each block is treated as a separate, addressable unit of data, and blocks can be combined to form a larger volume. 
- In AWS, block storage is provided by Amazon Elastic Block Store (Amazon EBS) service.
- Amazon EBS provides raw block-level access to your data, allowing you to easily create and attach volumes to Amazon EC2 instances. This makes it ideal for use cases such as databases, where low-latency, high-performance storage is required.
- Used on local networks
    - iSCI
    - Fibre Channel
- Best suited for use cases where low-latency, high-performance storage is required.

### File Storage
- Refers to a type of storage that is used to store data in the form of files and directories. 
- In AWS, file storage is provided by Amazon Elastic File System (Amazon EFS) service.
- Amazon EFS provides scalable file storage that can be accessed by multiple EC2 instances simultaneously, making it ideal for use cases such as file shares, big data processing, and content management. With Amazon EFS, you can scale your storage capacity without requiring changes to your application code or architecture.
- Uses similar called object sotrage in S3
- Used with NAS devices locally
- Best suited for use cases where scalability and multi-instance access to data is required.




## AWS Transfer
- A fully managed file transfer service that makes it easy to transfer files securely over SFTP (Secure File Transfer Protocol) and FTPS (File Transfer Protocol Secure) protocols to Amazon S3 or Amazon Elastic File System (Amazon EFS) file systems.
- AWS Transfer makes it easy to set up and manage file transfers to and from AWS. 
- You can set up transfer endpoints with just a few clicks and manage users and authentication with AWS Identity and Access Management (IAM).
- AWS Transfer integrates with Amazon S3 to automatically encrypt and store transfers, providing a secure and scalable solution for file transfer needs.

### Use Case
- Migrating data from on-premise data centers to the cloud.
- Automating file transfers to and from partners, customers, or other stakeholders.
- Transferring large amounts of data for big data analytics, backup and recovery, or other data-intensive applications.
- Cost-effective solution, as you only pay for the data transfers and the storage used, without the need to invest in, manage, and scale infrastructure.

## AWS Snow Family
## Snowcone
- 
