# RDS 
Back ups, Multi-AZ & Read Replicas

## Automated Backups
- Two different types of backups, automated and database snapshots
- **Automated**: Allows you to recover your db to any point and time within a "retention period".
  - Retention period is between one and 35 days.
  - Takes a full daily snapshot and will store transaction logs throughout the day
  - When doing a recovery, AWS will first choose the most recenty daily back up and then apply transaction logs relevant to that day.
  - Point in time recovery down to the second within retention period.
  - Enabled by default
  - Backup stored in S3 and free storage space equal to the size of your DB.
  - Backups are taken within a defined window.
  - Storage I/O may be suspended while data is being backed up
  - May experience elevated latency

- **Snapshots**: basically a snapshot of the database.
- Always done manually, stored even after you delete the original RDS instance, unlike automated backups.

## Restore
- Whenever you restore either Auto or Manual Snapshot, the restored version of the db will be a new DB with a new DNS endpoint.

## Encryption
- Supported for:
  - MySQL
  - Oracle
  - SQL Server
  - PostgreSQL
  - MariaDB
  - Aurora
- Done using the Key Management Service (KMS)
- Data stored at rest is the encrypted, as are its automated backups, read replicas, and snapshots.
- Encrypting an existing DB instance is not supported. 
  - In order to do so, you must create a snapshot, make a copy of that snapshot and encrypt the copy.

### Modify Database
- Set retention period
- Set start time
- Set duration

### Snapshots
- Clicking on snapshots, you can see snapshots created for the database


## Multi AZ
Any changes from sources targeting a DB will automatically replicate to another database in another zone. This is for dizaster recovery only.

If default node, distinguished by DNS, goes down it will reroute and point to the other node w/ copy. This is why you **never use IP address and use DNS only**.

- Multi AZ allows you to have an exact copy of your prod db in another AZ.
- AWS handles replication.
- When prod db is written to, it will auto sync with stand by db.
- In the event of planned db maintenance, db instance failure, or AZ failure, RDS will auto failover to standby.
- Not for improving performance, if you want performance use read replica
- Synchronous

Available for the following DBs:
- SQL Server
- Oracle
- MySQL Server
- Postgres
- MariaDB
- Aurora (by default)

## Read Replica
**Use case**: 90% of your db ops are reads, instead of having your servers hit the prod database, you have them access read replicas. This is a way to scale out your database. 

- You can also have read replicas of read replicas
- You can have read replicas in different AZs
- You can also have a read replica in a completely different region
- Read Replicas allow you to have a read-only copy of prod db
- Asynchronous replication from primary RDS instance. 
- For very read-heavy database workloads
- Must have automatic back ups in order to deploy
- Can have up to 5 copies of your database
- Each read replica will have it's own DNS end point
- Read replicas can be promoted to be their own databas, breaks replication
- FREE


Database Engine	Range of Provisioned IOPS	Range of Storage
MariaDB	1,000–40,000 IOPS	100 GiB–16 TiB
SQL Server, Enterprise and Standard editions	1000–32,000 IOPS	200 GiB–16 TiB
SQL Server, Web and Express editions	1000–32,000 IOPS	100 GiB–16 TiB
MySQL	1,000–40,000 IOPS	100 GiB–16 TiB
Oracle	1,000–40,000 IOPS	100 GiB–16 TiB
PostgreSQL	1,000–40,000 IOPS	100 GiB–16 TiB
