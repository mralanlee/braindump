# EBS
Create storage volumes and attach them EC2 instances. Once attached you can create a file system, run a database, or use them like any block device.

EBS volumes are placed in a specific Availability Zone where they are auto replciated to protect from data failure of a single component.

A virtual disk. Elastic Block Store.

Cannot attach a EBS volume to more than one EC2 at the same time.

## Types
- General Purpose SSD (GP2)
  - Balances both price and performance
  - Ratio of 3 IOPS per GB with up to 10,000 IOPS. Ability to burst up to 3000 IOPS for extended periods of time for volumes at 3334 GiB and above.
- Provisioned IOPS SSD (IO1)
  - Designed for I/O intensive apps such as **databases**
  - Use if you need more than 10,000 IOPS
  - Can provision up to 20K IOPS per volume
- Throughput Optimized HDD (ST1)
  - **Big Data**
  - Data warehouses
  - Log processing
  - Cannot be a boot volume
- Cold HDD (SC1)
  - **Lowest cost storage** for infrequently accessed workloads
  - File Server
- Magnetic (Standard)
  - **Lowest cost per gig of all EBS volume types that is bootable.**
  - Ideal for workloads where data is accessed infrequently and apps  where lowest storage cost is important
  - Legacy and not in comparison tables but still usable
  - Good for Dev


## Snapshots
- Snapshots exists on S3.
- Snapshots are time copies
- Incremental, only the blocks that have changed isnce last snapshot are moved to S3.
- If first time, it will take some time to create.
- If serves as root device, stop the instance before taking the snapshot
  - however you can snap while instance is running
- Create AMI's (Amazon Machine Images) from EBS-backed Instances and snapshots
- You can change sizes, and storage type  on the fly.
- Volumes will also be in the same availability zone as the EC2 instance.
- To move EC2 volume from AZ/Region you have to take a snap or AMI on it and then copy it in the new AZ/Region
- Snapshots of encrypted volumes are encrypted automatically
- Volumes restored from encryped are encrypted automatically
- You can share snapshots but only if they are unecrypted.
- Create Via CLI - `ec2-create-snapshot`

**DO THIS LAB AGAIN BEFORE EXAM**

## Raid Volumes
Raid = Redundant array of independent disks. Have multiple disks act as one.
  - Raid 0 - Striped, no redundancy, good performance
  - Raid 1 - Mirrored, redundancy
  - Raid 5 - Good for reads, bad for writes, AWS does not recommend ever putting RAID 5's on EBS. Writing via Parity.
  - Raid 10 - Striped and Mirrored, Good Redundancy, Good Performance.

Problems, Taking a snapshot of a RAID excludes data held in the cache by apps and OS.
Solution take an app consistent snapshot
- Stop the app from wriing to disk
- Flush all caches to the disk
- Freeze file system
- Unmount the RAID array
- Shut down the associated EC2
- Snapshot all the EBS volumes in the raid array

Used when you are not getting disk I/O required. Still need higher I/O.

## AMIs
Amazon Machine Images.
- Stop the instance
- Create a snapshot
- Copy snapshot to a different region (if preferred)
  - Option to encrypt snapshot
- Create Image
- Go to AMIs
  - Launch, setup EC2 instance
  - Storage, the root volume is encrypted (only if you select it being encrypted during snapshot)

You can select your AMI based on:
- Region
- Operating System
- Architecture (32 bit or 64 bit)
- Launch Permissions
- Storage for the Root Devices
  - Instance Store (Ephemeral Storage)
  - EBS Volumes

Once an instance is launched, you can only attach additional EBS volumes, not instance store volumes.

You can only reboot or terminate on Instance Store, you cannot stop or start. It is also created from a template stored in S3.

---
#### Roles
- More secure than storing access key and secret access key on individual instances
- Easier to manager
---
#### Instance Metadata
Used to get information about an instance (such as public ip)

`curl http://<ip>/latest/meta-data`
`curl http://<ip>/latest/user-data`
