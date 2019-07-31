# Storage Gateway
A service that connects to an on-premise software application with cloud based storage to provide seamless and secure integration between on-prem IT environment and AWS' storage infrastructure. Allows you to securely store data to AWS cloud.

- Your data center replicates to AWS S3 or Glacier.
- Storage gateway's software application is available to download as a vm image to host in data center.
- Supports VMWare ESXi or Microsoft Hyper-V.
- Once installed and associated with account, through AWS Management Console you can create a storage gateway option.

## Options
* File Gateway(NFS) - Store flat files on S3
* Volumes gateway (iSCSI) - Block based storage
  * Stored Volumes - entire copy of data
  * Cached Volumes - recently accessed data
* Tape gateway (VTL) - Create virtual tapes and sent to Glacier

### File Gateway
Stored as objects in S3 buckets, accessed through a NFS mount point.
Ownership, permissions and timestamps are durably stored in S3 in the user-metadata. Once objects are transferred to S3, they can be managed as native S3 objects, and bucket policies apply directly to objects stored in bucket.

Application server --> Storage Gateway -> Direct Connect / Internet / Amazon VPC - S3

### Volume Gateway
Interface presents your applications with disk volumes using iSCSI block protocol. Data written can be asynchronously backed up as point-in-time snapshots and stored in cloud as EBS snapshots. Snapshots are incremental backups that capture only changed blocks. All snapshot storage is compressed to minimize your storage charges.

**Stored Volumes**
Store your primary data locally, while asynchornously backing up to AWS. Provide your on-prem apps with low-latency access to entire datasets, while providing durable, off-site backups. 1GB to 16TB. **100%** backed up incremently.

**Cached Volumes**
Most frequently accessed data locally to storage gateway. Create 1GB to 32TB in size.

### Tape Gateway
Durable, cost-effective solution to archive data to AWS. VTL interface lets you leverage existing tape-based back up to store data on virtual tape cartridges. Each gateway is preconfigured with a media changer and tape drives. Supported by NetBackup, backup Exec, Veeam

