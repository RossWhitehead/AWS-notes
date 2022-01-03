## Comparison of AWS event-brokers

| Capability | SQS | SNS | Kinesis | MSK | Amazon MQ |
| -- | -- | -- | -- | -- | -- |
| Event Broker Type | Queue-oriented |
| Cluster Type | Serverless |
| Pros | Simple to use. Serverless, with no cluster adminstration and minimal configuration required. Very high throughout with standard queues. |
| Cons | Limited throughput with FIFO ordering. Proprietary protocol and APIs, so not portable. |