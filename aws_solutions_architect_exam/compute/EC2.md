# EC2
Amazon Elastic Compute Cloud, a web service that provides resizable compute capcity in the cloud. Reduces the time require to obtain and boot new server instances to iminutes allowing to quickly scale capacity both up and down as requirements change.

- Pay for capacity you actually use, as you use it.
- Provides developers the tools to build failure resilient apps

## Pricing Options
- **On Demand**, pay a fixed rate by the hour(or by the second) with no commitment.
  - Low cost and flexibility of EC2 without any upfront payment or long term commitment
  - Apps with short term, spiky, or unpredictable workloads that cannot be interrupted
  - Apps being developed or tested on EC2 for the first time.
- **Reserved**, capacity reservation and commitment of 1-3 year terms. Offers a significant distanct on hourly charge of instance.
  - Steady state or predictable usage
  - Reserved capacity
  - Upfront payments to reduce costs
    - Standard Reserved Instances (Up to 75% off on-demand)
    - Convertible Reserved Instance (Up to 54% off on-demand): ability to change attributes of the reserved instanced if exchange results in creation of RI of equal or greater value
    - Scheduled Reserve Instance allows to launch within the time window you reserve. Match capacity reservation to predictable recurring schedule that only requires a fraction of a day, week, or month.
- **Spot** allows you to bid for a price for instance capacity and can have flexible start and end times.
  - Apps that have flexible start and end times.
  - Apps that are only feasible at low compute prices.
  - Users with urgent need for large amounts of additional computing capacity.
  - If spot instance is terminated because price went up, will not be charged for a partial hour of usage. If terminated yourself, it will charge by the complete hour that instance ran.
- **Dedicated Hosts** Physical EC2 instance dedicated for your use. Help reduce costs by allowing you to use your existing bound software licenses.
  - Regulartory requirements without support for multi-tenant virtualization.
  - Licensing
  - Can be purchased on demand (hourly)
  - Can be purchased on reserve


## Family Types
- D for Density
- R for RAM
- M for main choice for general purpose apps
- C for computer
- G for graphics
- I for IOPS
- F for FPGA
- T cheap general purpose work
- P for Graphics (Pics)
- X for Extreme Memory

### At EC2 Creation
---
#### Configuration
- Able to create or assign VPC (Virtual Private Cloud)
- Able to create or assign subnet based on availability zone
- Shutdown behavior; you can specify the behavior that is to be performed on shutdown.
- Protect people from accidentally terminating the instance
- Monitor by cloudwatch logging
  - Every 5 minutes by default
  - Detailed monitoring can be turned on for every 1 minute but will charged
  - 
- Tenancy: This is where you can set dedicated hosts
- Advanced Details: Add in bootstrap scripts if needed (i.e. download Apache, Nginx, PHP, etc)

#### Storage
Add volume type/snapshots and size
By default, delete root volume on termination is checked. 
Root volumes cannot be encrypted, though you can use 3rd party tools to encrypt or you can copy it.

#### Tags
Key/value pairs. Seting tags can also show cost per tag.

#### Security Groups
Virtual firewalls
- Create new security group or select existing
- What type of traffic and port that you choose to allow
- Source is where it's coming from

When launching you have to select an existing key pair or create a new pair to access the EC2 instance

Move one EC2 instance from region to another, use snapshots by duplicating the sapshot

## IAM
1. Create a New Role
2. Select Amazon EC2

## Placement Groups
Two types of placement groups
1. Clustered Placement Group
2. Spread Placement Group

#### Clustered
Grouping of instances within a single availability zone. Placement groups are recommended for apps that need low network latency, high network throughput or both.

Only certain instances can be in launched in this group.

(i.e. Big Data) high ram, high cpu utilization

#### Spread Placement Group
Grouping of instances that are placed on distinct underlying hardware.

For apps that have a small number of critical instances that should be kept separate from each other.

Can span across multiple availability zone.

----
### Testing Tips

- Names for placement groups must be unique.

- AWS recommends homogenous instances within placement group.

- Cannot merge placement groups

- Cannot move existing intance into a placement group
