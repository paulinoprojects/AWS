# AWS Solutions Architect Associate: Data Storage Services - Glacier
### Overview
- Archival data storage
- Fractions of a penny per GB/month
- 3 Access Methods
    - Expedited (3-5 min)
    - Standard (3-5 hours)
    - Bulk (5-12 hours)
- Admins define the region for data storage
- Automatically stored with AES 256-bit encryption

### Glacier Integration
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
