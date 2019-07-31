# DynamoDB
- Fast and flexible NoSQL database for all apps that need consistent, single-digit millisecond latency at scale.
- Fully managed database
- Supports both document and key-value data models
- Flexible data model and reliable performance
- Perfect for mobile, web, gaming, ad-tech, IoT, and etc.,.
- UpdateTable does not consume capacity units

## Facts
- Always stored on SSD
- Spread across 3 geographically distinct data centers
- Eventual Consistent Reads (default)
  - Consistency across all copies of data is usually reached within a second. Repeating a read after a short time should return the updated data (Best Read Performance)
- Strongly Consisent Reads
  - Returns a result that reflects all writes that received a successful response prior to the read.
- Can contain 5 local secondary indexes on DynamoDB table

## Provision Throughput Capacity
- Write throughput $0.0065 per hours for every 10 units
- Read throughput $0.0065 per hour for every 50 units
- Storage costs of $0.25Gb per month

$Example:$
Your application needs to perform 1 million writes and 1 million reads per day, while storing 3 GB of data.

1 million writes / 24 hours / 60 minutes / 60 seconds = 11.6 writes per second.

Write capacity unit can handle 1 write per second, so you need 12 writes

1 million strongly consistent reads per day, need 12 read capacity units

Write capacity is billed in units of 10, read blocks of units of 50.

Total write = (0.0065/10) * 12 * 24 = $10.1872
Total Right = (0.0065/10) * 12 * 24 = $0.0374

## Key
Easy to scale, push button scaling
