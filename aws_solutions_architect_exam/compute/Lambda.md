# Lambda
- Triggered events that runs a function that talks to other services.
- Everytime something is done with lambda, a new instance of lambda is created.
  - 1 event = 1 function
- Scales out (not up) automatically
- Compute service where you can upload and create a Lambda function
- Takes of provisioning and managing servers
- No worries about OS, patching, scaling
- Event driven, runs code in response oto events.
- HTTP request handled through API Gateway
- Architectures can get extremely complicated, AWS X-Ray allows you to debug what's happening
- Lambda can do things globally, use it to back up S3 buckets to other buckets

## Pricing
- Based off of number of requests
  - First million requests are free. $0.20 per 1 million requests.
- Duration
  - From the time code begins executing until it returns or terminate, rounded by nearest 100ms. Maximum threshold is five minutes.

## COOL
- No Servers
- Continuous Scaling
- Super super super cheap

Practical Use Case: Amazon Echo
