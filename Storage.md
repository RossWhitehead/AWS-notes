# Storage

## S3

* Simple Storage Service.
* 11 9's (99.999999999) durability.
* Designed for 99.5% to 99.99% availability.

## Limits
* Each object, maximum of 5TB.
* Single PUT is limited to 5GB.
* Use muiltipart upload for objects > 100 MB.

## Storage Classes

* S3 Standard
    * General purpose store for frequently accessed data.
* S3 Intelligent-Tiering
    * Data with unknown or changing access patterns.
* S3 Standard-IA (Infrequent Access)
    * Long-lived less frequently accessed data.
* S3 One Zone-IA
    * Long-lived less frequently accessed data.
    * Same durability as Standard, but lower availability (99.5%)
* S3 Glacier
    * Long-term archive
* S3 Glacier Deep Archive
    * Long-term archive
* S3 Outposts
    * Store S3 data on-premise.

![](./images/aws-s3.png)

## Consistency Model

* Strong read-after-write consistency.

## Pricing Model

* Storage costs
    * can vary significantly by storage class.
* Request and Data Retrieval costs (Data retrieval from IA and  Glacier archives)
* Data transfer costs, except for:
    * Data transferred in from the internet.
    * Data transferred between S3 buckets in the same AWS Region. 
    * Data transferred from an Amazon S3 bucket to any AWS service(s) within the same AWS Region as the S3 bucket (including to a different account in the same AWS Region).
    * Data transferred out to Amazon CloudFront (CloudFront).

## Intelligent-Tiering Archive configuration

