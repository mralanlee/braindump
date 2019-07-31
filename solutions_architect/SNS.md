# SNS
- Simple Notification Services
- Web service that makes it easy to set up, operate, and send notifications from the cloud
- Publish messages from an application and immediately deliver them to subscribers
- Push Notifications to Apple, Google, Fire OS, Windows Devices and Android Devices in China with Baidu Cloud Push
- Can deliver SMS text messages or Email, SQS, or HTTP endpoints
- Can trigger lambda functions
- Group multiple reciepents using topics
  - Topic is an "access point" for allowing recipients to dynamically subscribe for identical copies of the same notification
  - One topic can support deliveres to multiple endpoint types
    - can group iOS, Android, and SMS recipients.
- Publishing a topic, SNS delivers appropriately formatted copies of your message to each subscriber
- Prevent message from being lost, all messages published to SNS are stored redundantly across multiple AZs
- **Creating a topic on SNS, a ARN is created**

## Benefits
- Instantaneous, push-based delivery (no polling)
- Simple APIs and easy integration with apps
- Flexible message delivery over multiple transport protocols
- Inexpensive, pay as you go with no upfront costs
- Web based AWS Management Console offers point and click interface


### SNS vs SQS
- Both messaging services in AWS
- SNS - Push, SQS - Polls (Pulls)


### SNS Pricing
- Users pay $0.50 per 1 million Requests
- $0.06 per 100,000 notification deliveries over HTTP
- $0.75 per 100 Notification Deliveries over SMS
- $2.00 per 100,000 notification deliveries over Email

### Subscribers
- HTTP
- HTTPS
- Email
- Email-JSON
- SQS
- Applcation
- Lambda
