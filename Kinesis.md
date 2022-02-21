# Kinesis

## Kinesis Data Streams

Collect and process large streams of data records in real time.

![](https://d1.awsstatic.com/Digital%20Marketing/House/1up/products/kinesis/Product-Page-Diagram_Amazon-Kinesis-Data-Streams.e04132af59c6aa1e9372cabf44a17749f4a81b16.png)

* Server-side encryption enables encryption of messages uisng KMS CMKs.
* Data is retained for 1 to 365 days.

### Capacity Modes

* On-demand
    * For unpredictable and variable throughput
    * 200 MiB/s and 200,000 records/s write capacity.
    * 400 MiB/s read capacity per consumer.
    * Up to 2 default consumers. However, Enhanced Fan Out (EFO) supports a higher number of consumers. 
* Provisioned
    * Fixed capacity for reliably estimated throughput.
    * Up to 500 shards (Can request a shard quota increase for an account).
    * Write capacity of 1 MiB/s and 1,000 records/s per shard.
    * Read capacity of 2 MiB/s per shard.

## Kinesis Data Firehose (Delivery Stream)

Deliver real-time streaming data to destinations such as S3, Amazon Redshift, Amazon OpenSearch Service, Splunk, custom HTTP endpoint, or HTTP endpoints owned by supported third-party service providers, including Datadog, Dynatrace, LogicMonitor, MongoDB, New Relic, and Sumo Logic.

* Sources: 
    * Kinesis Data Stream
    * Direct PUT from an application.
* Destinations:
    * Amazon OpenSearch Service
    * Amazon S3
    * Datadog
    * Dynatrace
    * Honeycomb
    * HTTP Endpoint
    * LogicMonitor
    * MongoDB Cloud
    * New Relic
    * Splunk
    * Sumo Logic
