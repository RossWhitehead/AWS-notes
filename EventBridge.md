# EventBridge

EventBridge is a serverless subscription-oriented event broker that delivers a stream of real-time data from event sources to targets.

Note. EventBridge was formerly called Amazon CloudWatch Events.

An Event Bus is an EventBridge pipeline that receives events and the applies rules to route the events to targets.

## Why use EventBridge rather than SNS

* SaaS integration
    * Supported SaaS providers can be authorised to send events directly from their EventBridge event bus to event buses in your account. This replaces the need for polling or webhook configuration, and creates a highly scalable way to ingest SaaS events directly into your AWS account.
* Schema Registry
    * Enables discover and manage OpenAPI schemas for events.
* Availability
    * 99.99% SLA compared to 99.9% for SNS
* Broader range of targets
    * EventBridge has 17 targets including AWS Lambda, Amazon SQS, Amazon SNS, AWS Step Functions, Amazon Kinesis Data Streams, Amazon Kinesis Data Firehose, API Gateway REST API endpoints and Amazon Redshift clusters.
    * SNS has the following targets: HTTP(S), SMS, SNS Mobile Push, Email/Email-JSON, SQS, Lambda functions.



## Why use SNS over EventBridge

* FIFO queues
    * SNS FIFO topics provide guaranteed ordering. EventBridge event buses do not.  
* Application to Person message delivery
    * SMS, SNS Mobile Push and Email/Email-JSON targets.

  

