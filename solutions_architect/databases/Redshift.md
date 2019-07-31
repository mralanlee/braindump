# Redshift
- Fast and powerful
- Fully managed
- Petabyte-scale, data-warehouse
- 1024KB/1MB Block Size for columnar storage

## Pricing
- $0.25 per hour with no commitments or upfront costs
- Scale to a petabyte or more for $1,000 per terabyte per year
- Less than a tenth of most other data warehousing solutions
- **Compute Node Hours**
  - 1 unit per node per hour
  - Not charged for leader node hours
- Back Up
- Data transfer (only within a VPC, not outside it)

## Configuration
- Starts with Single Node (160gb)
- Scale: Multi-Node
  - Leader Node (manages client connections and receives queries)
  - Compute Node (store data and perform queries and computations). Up to 128 compute Nodes.

## Features
### Columnar Data Storage
- Instead of organizing by rows, Redshift organizes data by column. 
- Column based systems are ideal for data warehousing and analytics
  - Queries often involve aggregates performed over large data sets.
  - Columnar data is stored sequentially on the storage media, require far fewer I/Os, greatly improving query performance
- Stores data sequentially

### Advanced Compression
- Stores can be compressed much more than row-based ata stores because similar data is stored sequentially on disk.
- Compression techniques and can often achieve significant compression relative to traditional data stores.
- Doesn't require indexes or materialized views
- Uses less space than traditional relational database systems.
- Automatically samples data and selects most appropriate compression scheme

### Massive Parallel Processing (MPP)
- Automatically distributes data and query load across nodes.
- Easy to add nodes to your data warehouse
- Faster query performance as data warehouse grows.

## Security
- Encrypted in transit using SSL
- Encrypted at rest using AES-256 encryption
- Takes care of key management (by default)
  - Can manage your own keys through HSM
  - AWS KMS

## Availability
- Currently only available in 1 AZ
- Can restore snapshots to new AZ's in the event of an outage
