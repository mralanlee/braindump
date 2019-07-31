# Databases
**Relational Database** has been around since the 70s. Similar to a spreadsheet:
- Database
- Tables
- Row
- Fields (Columns)

**NoSQL**
JSON format, key value pairs

### Data Warehousing
Used for Business Intelligence. Used to pull in very large and complex data sets.

##### OLTP vs OLAP
Online transaction processing (OLTP) differs from Online analytics processing (OLAP) based on the types of queries run.

**OTLP Example:** (Think RDS/Dynamo)
Pulls a row of data such as Name, Date, Address to Deliver to, Delivery Status... etc

**OLAP Example:** (Think Redshift)
Net Profit for EMEA and Pacific.
- Large number of records
- Data warehousing dbs use different architecutre from a db perspective and infrastructure layer

## Elasticache
- In memory cache in the cloud
- Performance of web apps by allowing to retrieve information from fast, managed, in-memory cache instead of disk based dbs.
- Memcached
- Redis


