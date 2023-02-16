
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
- Buckets: Functions like a hard drive
- Region: Location where your bucket will be hosted, closer to the user.
- Objects: Functions like a file
- Keys: Serves as the logical name of an object (the file name)
- Object URLs: Each object in the bucket has a URL
- Eventual Consistency: may take time to get copy across avaliability zones
  - Great for static website hosting
### Common S3 Operation
- Creating and deleteing buckets
- Write objects
- Reading objects
- Deleting objects
- Managing object propertiies 
- Listing keys in buckets
### Representation State Trnasfer (REST)
- S3 API
- Maps HTTP methods to CRUD operations
  - Create uses PUT or POST
  - Read uses GET
  - Update uses POST or PUT
  - Delete uses DELETE
