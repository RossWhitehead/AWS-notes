## EFS

* Scalable file storage for multiple EC2 instances
* Totally elastic – once you’ve spun up an EFS instance, you can add add files without worrying about provisioning or disturbing your application’s performance.
* NFS compatible.
* Mount to EC2 or on-prem Linux server over DirectConnect.
* Can be accessed by multiple EC2 instances within a VPC.
* Create a mount target for each AZ that contains EC2 instances.
* Storage Classes:
    * Regional - High availability
        * EFS Standard.
        * EFS Standard IA (Infrequent Access).
    * One-Zone
        * EFS One Zone.
        * EFS One Zone IA.
* Automatic backups to S3 with AWS Backup.
* Lifecyle Management
    * None to 90 days since last access.
    * Moves infequently accessed files into IA.
* Performance Modes:
    * General purpose - latency sensitive use cases.
    * Max I/O - High throughput.
* Throughput modes:
    * Bursting
        * Throuput scales with the size of the file system.
        * Can burst to 100 MiB/s of metered throughput
    * Provisioned - Configure provisioned and max throuput.
        * Provisoned Throughput 1-1024 MIB/s.
        * Max throughput.
        * For applications with high throuput to storage (e.g. web server or CMS).

## FSx

* Windows File System compatible.


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
