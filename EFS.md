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
