# Security Group
A virtual firewall.
Security groups are stateful. If there is an inbound rule, that rule would be applied to something outbound, automatically.

## Inbound Rules
- Deleting/Updating/Creating inbound (HTTP) rules happens immediately
- All inbound traffic is blocked by default
- Cannot block specific IP Addresses using Security Groups, use Network Access Control Lists
## Outbound Rules
- Rules for traffic coming out
- All outbound traffic is allowed by default

You can't deny things from coming in, only allow them. (Whitelisting allowed, no blacklisting)

You can associate multiple security groups to a single EC2 instance
