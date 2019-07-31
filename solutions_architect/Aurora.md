# Aurora
- Aurora only runs on AWS and cannot be installed locally
- MySQL compatiable
- Relational Database engine that combines speed and availability of high-end commercial dbs
- Simplicity and cost-effectiveness of open source dbs
- Five times better performance than MySQL
- Price point of one tenth of a commercial db while delivering similar performance and availability

## Scaling
- Start with 10gb, scales in 10gb increments to 64tb (storage autoscaling)
- Compute resources can scale up to 32vCPUs and 244GB of memory
- Push button scaling, but not like DynamoDB, will be down time.
- 2 copies of data is contained in each AZ, with min of 3 AZs, 6 copies of data.
- Designed to transparently handle loss of up to two copies of data without affecting DB write availability and up to three copies without affecting read availability.
- Self healing. Data blocks are continuously scanned for errors.

## Replicas
- 2 types are available
  - Aurora Replicas (15 currently)
  - MySQL read replicas (5 currently)

Key difference, if failure than it would automatically failover to your Aurora Replica, not mysql.
