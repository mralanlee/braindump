# Elastic Load Balancers
Balances the load across AWS

#### Three types
1. Application Load Balancer (ALB)
2. Network Load Balancer (NLB)
3. Classic Load Balancer

##### Application Load Balancer
- Best suited for load balance of HTTP and HTTPS traffic. 
- Operates at layer 7 and are application-aware. 
- Can create advanced request routing, sending specific requests to specific web servers.

##### Network Load Balancer
- Load balancing TCP traffic where extreme performance is required.
- Operating at connection level (layer 4)
- Capable of handling million of requests per second while maintaing ultra-low latencies.
- For extreme performance

##### Classic Load Balancer
- Elastic load balancers
- Load HTTP/HTTPS applications, and layer 7-specific features such as x-forwarded and sticky sessions.
- Strict Layer 4 load balancing for applications to rely purely on the TCP protocol.
- 504 error, gateway timeout, means its having issues connecting to the Web Server.

#### Exam Tips
- If you need the IPv4 address of your end user, look for the X-Forwarded-For header
- Instances monitored by ELB are reported as InService or OutofService
- Health checks, checks the instance healh
- LBs have heir own DNS name. Never given IP address
- Sticky sessions
  - Duration-based session stickiness and application-controlled session stickiness.
