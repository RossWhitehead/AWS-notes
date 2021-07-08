# AWS-notes

## EC2
### Placement Groups
3 strategies: Cluster; Partition; Spread
#### Cluster Strategy
* Places instances in the same AZ.
* Low latency, high throughput.
* Best to use single lauch request. Adding instances may result in insufficient capacity error.
#### Partition Strategy
* Has a requested number of partitions.
* Partitions can span AZs.
* When launching instances, specify which placement grouo, partition (or auto distribution), and AZ.
* Each partition has a distinct rack with independent network and power supply.
* Large distributed, replicated workloads such as HDFS and Cassandra.
#### Spread Strategy
* Each instances has a distinct rack with independent network and power supply.
* Can span multiple AZs.

### Instance Profiles and IAM Roles
* Instance profiles allows an EC2 instance to assume a role on startup.
* Can be applied to multiple instances.
* How to use and instance profile:
  - Create a role with the EC2 service as a trusted entity.
  - Assign IAM role (instance profile) to EC2 instances when lauching.
* How to change an EC2 instances role:
  - Actions -> Security -> Modify IAM Role
