# Kinesis
Data that is generated continuously by thousands of data sources, which typically send in the data records simultaneously, and in small sizes (order of Kilobytes)
- Purchases from online stores
- Stock Prices
- Game Data (as gamer plays)
- Social Network Data
- Geospatial Data
- IoT Sensor Data

Kinesis is a platform on AWS that you send your streaming data to. Kinesis makes it easy to load and analyze streaming data and provide availability for you to build your own custom apps for business needs.

### 3 Core Kinesis Services
- Kinesis Streams
  - Producers (EC2, mobile, PC) sending data to Kinesis Streams
    - Data is sent in shards
      -  A shard is 5 transactions per second for reads
      -  Up to a max total data read rate of 2MB per second
      -  Up to 1000 records per second for writes
      -  Up to Max total data write rate of 1mb per second
      -  Multiple shards of data in a stream
        - Capacity of stream is a function of the number of shards that you specify for the stream.
        - Total capacity of the stream is the sum of the capacities of its shards
    - Once data is stored in shards, it is sent to consumers (fleet of EC2 instances)
    - They can then send the data to other AWS services
  - By default 24 hour retention but can be increased by 7 days
- Kinesis Firehose
  - Producers
    - Sends data in Firehose
    - Don't have to worry about shards, completely automated
    - Don't have to worry about data consumers, can use lambda to analyze
    - Send data directly to something like S3
    - No data retention; data is either analyzed by lambda or sent to S3 or other locations (Redshift, if this route it has to go to S3 first)
- Kinesis Analytics
  - Allows you to run SQL queries as the data is in Firehose or Streams
  - SQL Query can be used to store in S3, Redshift, or Elasticsearch Cluster

### Exam Tips
- Know difference between kinesis streams and kinesis firehose.
- Given scenario questions and you must choose most relevant service
- Understand what Kinesis Analytics is
- Used to consume big data
- Stream large amounts of social media, news feed, etc in the cloud
- process large amounts of data
  - Redshift for BI
  - Elastic Map Reduce for big data processing
