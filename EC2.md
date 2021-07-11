# EC2
## Instance Types
* General purpose
   - Similar CPU, RAM, and network.
   - Lowest cost.
* Compute optimized
   - Higher CPU performance.
   - Scientific modelling, Ad serving, Video encoding.
* Memory optimized
   - Large in-memory datasets.
   - High performance databases, distributed in-memory caches, big data analytics.
* Acceleated computing
   - Hardware accelerators like GPUs and FPGAs.
   - Machine and deep learning, advanced anaytics, graphics workloads, genomics.
* Storage optimized
   - High I/O to large local data sets.
   - NoSQL dbs, datawarehousing, distributed file systems, log processing.
## EC2 Storage Options
### EBS
* Volume types:
    * SSD
        * General purpose (default).
        * Provisoned IOPS - latency sensitive transctional workloads.
    * HDD
        * Throughput optimized - frequently accessed throughput intensive workloads, large data sets, large IO sizes.
        * Cold HDD - lowest cost.
* EBS Multi-Attach enables provisoned IOPS volumes to be attached to up to 16 AWS Nitro instances. 
### EFS
* Manged NFS file system.
* Highly available - multi-AZ redundancy within a region.
* Auto-scalling - pay for what you use.
* Multiple instances can access the file system - great for shared files.
* Storage classes
    * Standard
    * Standard-IA (Infrequent Access)
    * One-Zone
    * One-Zone-IA (Infrequent Access)
* Lifecyle management - files can be automatically moved from Standard to Infrequent Access storage classes after a configured time since last access (0-90 days).
* Performanace modes:
    * General purpose
        * Latency-sensitive use cases, such as web servers and CMS.
    * Max I/O
        * High levels of and IOPS. Massive concurrent Access.
* Throughput modes:
    * Bursting
        * Scales with size of file system. Can burst to burst to 100 MiB/s.
    * Provisoned
        * For applications with high throughput to storage (MiB/s per TiB) ratios, or with requirements greater than those allowed by the Bursting Throughput mode.
### Instance storage
* Temporary block-level storage.
* Physically attached to host computer.
* Data is lost when instance terminates, but preserved during a reboot.
* Instance store backed instances cannot be stopped or hibernated.
## Placement Groups
3 strategies: Cluster; Partition; Spread
### Cluster Strategy
![](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/images/placement-group-cluster.png)
* Places instances in the same AZ.
* Low latency, high throughput.
* Best to use single lauch request. Adding instances may result in insufficient capacity error.
### Partition Strategy
![](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/images/placement-group-partition.png)
* Has a requested number of partitions.
* Partitions can span AZs.
* When launching instances, specify which placement grouo, partition (or auto distribution), and AZ.
* Each partition has a distinct rack with independent network and power supply.
* Large distributed, replicated workloads such as HDFS and Cassandra.
### Spread Strategy
![](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/images/placement-group-spread.png)
* Each instances has a distinct rack with independent network and power supply.
* Can span multiple AZs.

## Instance Profiles and IAM Roles
* Instance profiles allows an EC2 instance to assume a role on startup.
* Can be applied to multiple instances.
* How to use an instance profile:
  - Create a role with the EC2 service as a trusted entity.
  - Assign IAM role (instance profile) to EC2 instances when lauching.
* How to change an EC2 instances role:
  - Actions -> Security -> Modify IAM Role
