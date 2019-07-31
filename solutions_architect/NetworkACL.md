# Network Access Control Lists vs Security Groups

## Network Access Control Lists
- You can ever associate a subnet to one network ACL
- By default, when you create a Network ACL, Inbound rules are setup by default to deny everything inbound and outbound
- VPC automatically comes with a default network ACL, and it allows all outbound and inbound traffic
- Each subnet in your VPC must be associated with a network ACL. If not, it is associated assigned default Network ACL.
- Associate a network with multiple subnets, not the other way around. If you have associate a network  ACL with a subnet, the previous assignment is removed
- Network ACLs contain a numbered list of rules that is evaluated in orer, starting with the lowest numbered rule.
- Network ACLs have separate inbound and outbound rules, and each rule can either allow or deny traffic.
- Network ACLs are stateless; responses to allowed inbound traffic are subject to the rules for outbound traffic (and vice versa)
- Allow Emphemeral Ports on the Outbound rules
- Can block IP Addresses

## Security Groups


### Ephemeral Port
Short lived transport protocol port for TCP, UDP, or SCTP as port assignment for the client end of a client-server communication to a well-known port on a server.


### Rules
Rules are evaluated in numerical order.
$Example$: 
Rule 100, allow all HTTP requests
Rule 101, block specific access on HTTP port for IP Address

Rule 100 wins.
---
$Example$: 
Rule 100, allow all HTTP requests
Rule 99, block specific access on HTTP port for IP Address

**Rule 99 wins.**
