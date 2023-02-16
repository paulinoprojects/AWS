
# AWS Solutions Architect Associate: Data Storage Services - S3
Reference: https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html

## Design Considertions for Storage Services
- Size
  - What types of data are you storing?
  - Storage size requirements? -GB, -TB -PB?
- Performance
  - How accessable do you need your data?
- Cost
  - Find the balance between performance, security, and operational cost.
- When selecting storage class, its important to consider monitoring, automation, and retreival fees. 
 
### Types of Storage Services
- <b>Simple Sotrage Service (S3)</b>
- Glacier
- CloudFront
- Elastic Block Storae (EBS)
- Storage Gateway
- Snow Family
- Databases

#### Block Storage
- Refers to a type of storage that is used to store individual blocks of data, rather than files. Each block is treated as a separate, addressable unit of data, and blocks can be combined to form a larger volume. 
- In AWS, block storage is provided by Amazon Elastic Block Store (Amazon EBS) service.
- Amazon EBS provides raw block-level access to your data, allowing you to easily create and attach volumes to Amazon EC2 instances. This makes it ideal for use cases such as databases, where low-latency, high-performance storage is required.
- Used on local networks
    - iSCI
    - Fibre Channel
- Best suited for use cases where low-latency, high-performance storage is required.

#### File Storage
- Refers to a type of storage that is used to store data in the form of files and directories. 
- In AWS, file storage is provided by Amazon Elastic File System (Amazon EFS) service.
- Amazon EFS provides scalable file storage that can be accessed by multiple EC2 instances simultaneously, making it ideal for use cases such as file shares, big data processing, and content management. With Amazon EFS, you can scale your storage capacity without requiring changes to your application code or architecture.
- Uses similar called object sotrage in S3
- Used with NAS devices locally
- Best suited for use cases where scalability and multi-instance access to data is required.

# S3 
### Storage Class
- Standard - Frequently accessed data.
- Standard Infrequent Access (IA) - Infrequently accessed data.
- 1 Zone IA - Infrequent accessed data, non-critical.
### Storage Class Features
- Object storage
- Distributes across at least three avaliability zones by default (Except: 1A = 1 Zone but least expensive)
- Support encryption and data automatic classification
- Big data analytics can run directly against stored data (no need to transfer data to a database to run analytics)

### Getting data into S3
- API (Application Programming Interface)
- AWS Direct Connect 
- Storage Gateway 
- Kinesis Firehose
- Transfer Acceleration
- Snow Family
  - Snowball
  - Snowball Edge
  - Snowmobile 

### S3 Terminology
- Buckets: Functions like a hard drive.
- Region: Location where your bucket will be hosted, closer to the user.
- Objects: Functions like a file.
- Keys: Serves as the logical name of an object (the file name).
- Object URLs: Each object in the bucket has a URL.
- Eventual Consistency: May take time to get copy across avaliability zones.
- Prefixes: A string of characters that comes before the object name in the object key. For example, if you have a bucket called "my-bucket" and a file called "images/photo.jpg", the prefix would be "images/".
- Delimiters are used to further organize objects into logical groupings. For example, if you have a prefix "images/" and objects with keys "images/photo.jpg" and "images/logo.png", you could use a delimiter to group the objects by file type, creating subfolders "images/jpg/" and "images/png/".

### Common S3 Operation
- Creating and deleteing buckets
- Write objects
- Reading objects
- Deleting objects
- Listing keys in buckets
- Managing object propertiies 
- Object properties include storage class, encryption, metadata, and tags.
    - Metadata is used to define the purpose of the object.
    - Tags are usedto search, organize, and manage access. Objects can have up to 10 tags.
- When creating an S3 bucket folders, prefixes are added to objects to that they appear as folders.

#### S3 Bucket Properties
- Static Website Hosting, admins can enable their bucket to host a website. 
- Encryption (storage secuirty, data at rest not transit), admins can encrypt the bucket and/or objects. 
- Permissions/Access can be set at the bucket level for baseline, then individual object permissions can be added to the baseline of the bucket. 
- Lifecycle Rules for objects to can be applied to save on costs. 
    - Unused objects can be configured to automatically move to Infrequent Access after 30 days, then Glacier after 60 days of being inactive.  


# Storage Gateway - Used to store files as objects in AWS S3
1. File Gateway - Local cache for low-latency access to your most recently used data.
2. Volume Gateway - Block storage in AWS S3 with point-in-time backups as Amazon EBS snapshots.
3. Tape Gateway - Back up data to S3 and archive in Glacier using your exisiting tape-based processess.
