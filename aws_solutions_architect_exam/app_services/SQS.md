# SQS
- Web service that gives you access to a message queue
- Store messages while waiting for a computer to process them
- Distributed Queue System that allows apps to quickly and reliably queue messages that one component in  the application generates to be consumed by another.
- Queue is temporary repistory for message awaiting processing.
- Decouple components of an app so they can run independently.
- Messages can contain up to 256 KB of text in any format
- Queue acts as a buffer between component producing and saving data, and component receiving the data for processing
- Solves issues that arise if producer is producing work faster than the consumer can process it.


### Pricing
- Billed in increments of messages sizes of 64kb

### Standard Queues
- By default all queues are standard queue
- Nearly unlimited number of transactions per second.
- Guarantee that a message is delivered at least once
- Ocassionally, more than one copy of a message might be delivered out of order
- Best-effort ordering which ensures thage messages are generally delivered in the same order they are sent


### FIFO Queues
- Messages are first in first out basis, deliver exactly ordered processing.
- Strictly preserved and a message is delivered once and remains available until a consumer processes and deletes it
- Duplicates are not introduced into the queue
- Supports message groups that allow multiple ordered message groups wihtin a single queue.
- FIFO queues are limited to 300 transactions per second, but have all capabilities of standard queues

## SQS Key facts
- Pull based, not push based
- Messages are 256kb in size
- Messages can be kept in the queue from 1 minute to 15 days
- Default retention period is 4 days
- Guarantess that your messages will be processed at least once

## SQS Visibility Timeout
- Amount of time that the message is invisible in the SQS queue after ar eader picks up that message.
- Provide the job is processed before the visibility time out expires, message will be deleted from queue
- If job is not processed within that time, message will become visible again and another will process it
- Could result in same message being delivered twice
- Default visibility timeout is 30 seconds
- Increase it if your task takes > 30 seconds
- Max is 12 hrs

## Long Polling
- Retrieve messages from your SQS Queues
- Regular *Short Polling* returns immediately, *Long Polling* doesn't return a response until a message arrives in the message queue, or until long poll times out
- Long polling can save money
