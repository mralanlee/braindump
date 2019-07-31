# DNS
DNS is a domain name service. DNS used to convert human friendly domain names into a IP address. IP Addresses are used by computers to identify each other

IPv4 32 bit field has over 4 billion different addresses

IPv6 created to solve depltion issue and has an address space of 128 bits.

# Route 53
- Supports DNS records, including MX.
- Named 53 because of port
- Supports zone apex records (naked domain names)
- Limit of 50 domain names, and can be extended by contacting AWS

## SOA Records
Information about:
- Name of the saerver that supplied the data for the zone
- Admin of the zone
- Current version of the data file
- Number of seconds a secondary name should wait before checking for updates
- Number of seconds a secondary name should wait before retrying a failed zone transfer.
- Max number of seconds that a secondary name server shcan use data before it must be refreshed or expired.
- Default number of seconds for TTL (time to live) file on resource records.

## NS Records
Name Serve records which contains used by top level domain servers to direct traffic to DNS server which contains authorative DNS records.

### A records
IP address is the A record. Used by computer to translate the domain to IP.

## TTL
Length of time a DNS is cached on either Resolving Server or the users loal PC. Lower the TTL, faster changes to DNS records take to propogate throughout the internet.

## CNAMES
Canonical Name used to resolve one domain name to another 

## Alias
Like a CNAME but you can use it to reference individual AWS resources like load balancers or CloudFront distributes

---
## Tips
ELB's do not have pre-defined IPv4 addresses, you resolve them through DNS

Always choose an alias record over CNAME

### 5 types of Routing Policies
- Simple: Round robin, used for a single server
- Weighted: Good for A/B testing, split routing
- Latency: Enducers, based of latency timing
- Failover: Data Recovery and sent to healthy servers if something fails a health check
- Geolocation: Based off of where users are
