# Storage Gateway

* AWS Storage Gateway connects an on-premises software appliance with cloud-based storage.

## S3 File Gateway

![](https://docs.aws.amazon.com/filegateway/latest/files3/images/file-gateway-concepts-diagram.png)

* File interface into S3.
* Network File System (NFS) and Server Message Block (SMB).
* A software appliance, or gateway, is deployed into your on-premises environment as a VM.
* Provides low-latency access to data through transparent local caching.
* Objects are encrypted with Amazon S3–server-side encryption keys (SSE-S3).

## S3 Tape Gateway

![](https://docs.aws.amazon.com/storagegateway/latest/tgw/images/Gateway-VTL-Architecture2-diagram.png)

* Cloud based virtual tape storage.
* Cost-effectively and durably archive backup data in S3 Glacier Flexible Retrieval or S3 Glacier Deep Archive.
* Eliminates the operational burden of provisioning, scaling, and maintaining a physical tape infrastructure.
* You can deploy Storage Gateway either on-premises as a VM appliance, or in AWS on EC2.

## Volume Gateway

![](https://docs.aws.amazon.com/storagegateway/latest/vgw/images/aws-storage-gateway-cached-diagram.png)

* Cloud-backed storage volumes that you can mount as Internet Small Computer System Interface (iSCSI) devices from your on-premises application servers.
* You can deploy a Volume Gateway either on-premises as a VM appliance, or in AWS as an Amazon EC2 instance.
* The gateway supports the following volume configurations:
    * Cached Volumes
        * Store data in Amazon Simple Storage Service (Amazon S3) and retain a copy of frequently accessed data subsets locally.  
        * Offers a substantial cost savings on primary storage and minimize the need to scale your storage on-premises.
        * Low-latency access to your frequently accessed data only.
    * Stored Volumes
        * All data is stored locally.
        * Asynchronously back ups of point-in-time snapshots to Amazon S3.  
        * Offers durable and inexpensive backups.
        * Low-latency access to all data.

## FSx File Gateway

![](https://docs.aws.amazon.com/filegateway/latest/filefsxw/images/file-fsx-architecture.png)

* Low latency and efficient access to in-cloud FSx for Windows File Server file shares from your on-premises facility.
* Eliminate on-premises file servers and consolidates all their data in AWS to take advantage of the scale and economics of cloud storage.
