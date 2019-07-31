# NAT Instances
- When creating a NAT instance, Diable Source/Destination Check on the instance.
- NAT instances must be in a public subnet.
- There must be a route out of the private subnet to the NAT instance in order for this to work.
- Amount of traffic that NAT instances can support depends ont he instance size. Bottlenecking increases the instance size
- Create high availability using Autoscaling Groups, multiple subnets in different AZs, and a script to automate failover.
- Behind a security group

# NAT Gateway
- Preferred by enterprises
- Scale automatically up to 10Gbps
- No Need to Patch
- Not associated with security groups
- Automatically assigned a public IP address
- Remember to update your route tables, always
- No need to disable source/destination checks
- More secure than a NAT instance
  - no SSH Access
  - No need to patch security updates
  - Amazon will manage this for you
