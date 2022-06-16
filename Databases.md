# Databases

## RDS

* Managed relational database service.

### Engine options

* Amazon Aurora
    * MySQL and PostgreSQL compatible enterprise-class database.
    * Up to 5 times the throughput of MySQL and 3 times the throughput of PostgreSQL
    * Up to 64TB of auto-scaling SSD storage
    * 6-way replication across three Availability Zones
    * Up to 15 Read Replicas with sub-10ms replica lag
    * Automatic monitoring and failover in less than 30 seconds.
    * Capacity Types:
        * Provisioned
            * Consists of one or more DB instances and a cluster volume that stores your data. You can adjust the number and instance classes of the DB instances depending on your workload. Additional DB instances help to increase read scalability and high availability. The cluster volume spans multiple Availability Zones (AZs), with each AZ having a copy of the DB cluster data.
        * Serverless
            *Provides a relatively simple, cost-effective option for infrequent, intermittent, or unpredictable workloads. The cluster consists of a single DB instance and a cluster volume that stores your data. Aurora scales the compute capacity of the DB instance to match your application's usage. Aurora also starts up the cluster when needed and shuts it down when it's not in use. The cluster volume has the same benefits as for a provisioned cluster.
* MySQL
* MariaDB
* PostgreSQL
* Oracle
* SQL Server.

## DynamoDB

* Multi-AZ NoSQL.
* Cross-region replication.
    * Utilises DynamoDB Streams.
* Eventual-consistency and strong-consistency options.
* ACID transaction.
    * Within a region.
    * Serializable or read-commited depending on operation.
        * Serializable: DeleteItem, PutItem, UpdateItem, GetItem
        * Read-committed: BatchGetItem, BatchWriteItem, Query, Scan.    
* Each table has a primary key and an optional sort key (i.e. composite PK index).
* Can have many secondary indexes.

### Compatibility Modes

* On-demand
    * Simplify billing by paying for the actual reads and writes your application performs.
* Provisoned
    * Manage and optimize your costs by allocating read/write capacity in advance.
    * Optional auto-scaling of tables and secondary indexes based on demand.

### DAX

 * Amazon DynamoDB Accelerator (DAX) is a fully-managed, highly-available, in-memory caching service for DynamoDB.

### DynamoDB Streams

![](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/images/HowItWorksStreams.png)

* Amazon Kinesis Data Streams for DynamoDB
    * Captures item-level changes in your table, and replicates the changes to a Kinesis data stream. You then can consume and manage the change information from Kinesis. Charges apply.
* DynamoDB Streams
    * DynamoDB Streams captures a time-ordered sequence of item-level modifications in any DynamoDB table and stores this information in a log for up to 24 hours. 
    * API for reading streams is exposed on it's own endpoint.

## ElastiCache

* Memcached or Redis
* Which to choose?
    * Backup/Restore: Memcached = No, Redis = Yes.
    * Replication: Memcached = No, Redis Cluster = Yes.
    * Sharding: Memcached = Yes, Redis Cluster = Yes.

## AWS Neptune

* Graph DB

## AWS DocumentDB

* Document DB

