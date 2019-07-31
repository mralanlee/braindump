# CloudFront

## CDN - Content Delivery Network
A content delivery network is a system of distributed servers (network) that deliver webpages and other web content to a user based on the geographic location of the user. (CSS, JS, HTML files)

### Key Terminology
* **Edge Location** - Where content can be cached, separate to AWS Region/Availability Zone
* **Origin** - Original of all the files that the CDN will distribute. Can be S3 bucket, EC2 instance, ELB or Route 53. Where original files are.
* **Distribution** - Name given to the CDN which consists of a collection of Edge Locations.
* **Web Distribution** - Used for websites
* **RTMP** - Used for media streaming

### What is CloudFront
- Deliver an entire website, including dynamic, static, streaming and interacting content using a global network of edge locations.
- Requests are automatically routed to the nearest edge location.
- Optimized for the following:
  * S3
  * Elastic Compute Cloud
  * ELB
  * Route 53
  * Also works with non-AWS origin server

### Exam Tips
- Edge locations are not just READ only
- Objects are cached for the life of the TTL (time to live)
- Can clear cached objects, but you will be charged
