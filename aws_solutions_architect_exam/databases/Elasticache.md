# Elasticache
Web service that makes it easy to deploy, operate, scale an in-memory cache in the cloud. Improves performance of web apps by allowing you to retrieve info from fast, managed, in-memory caches, instead of using slow disk-based storage.

Can be used to significantly improve latency and throughput for many read-heavy application workloads, or compute intensive workloads. 

Caching improves application of performance by storing critical piece of data in memory for low-latency access. May include the results of I/O-intensive DB queries or the results of computationally-intensive calculations.

## Redis
- Popular open-source in-memory key-value store.
- Supports data structures such as sorted sets and lists.
- Elasticache supports Master/Slave replication and Multi-AZ which can be used to achieve cross AZ redundancy

## Memcached
- Widely adopted memory object caching system.
- Elasticache is protocol compliant with memcached
- Popular tools working with Memcached environments will work seamlessly

## Exam Tips
- Usually given a scenario where a particular db is under a lot of stress/load. Asked which service would be used.
- Good choice if your DB is particularly read heavy and not prone to frequent change
- Redshift is a good answer if reason your DB is feeling stress because of managemnt keep running OLAP transactions on it
