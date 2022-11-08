# EC2
## Instance Types
* General purpose
   - A a balance of compute, memory and networking resources.
   - Low cost.
   - Good for web servers and code repositories.
   - e.g. **T3**: offer burstable performance. Baseline CPU with ability to burst above that on demand.
* Compute optimized
   - High CPU performance.
   - Scientific modelling, Ad serving, Video encoding.
   - e.g. **C4**
* Memory optimized
   - Large in-memory datasets.
   - High performance databases, distributed in-memory caches, big data analytics.
   - e.g. **R6g**
* Acceleated computing
   - Hardware accelerators like GPUs and FPGAs.
   - Machine and deep learning, advanced anaytics, graphics workloads, genomics.
   - e.g. **P4**
* Storage optimized
   - High I/O to large local data sets.
   - NoSQL dbs, datawarehousing, distributed file systems, log processing.
   - e.g. **I3**

### Snaphots

![](https://k2y3h8q6.stackpathcdn.com/wp-content/uploads/2018/12/AWS-Training-Amazon-EC2-3.jpg)
## Placement Groups
3 strategies: Cluster; Partition; Spread
### Cluster Strategy
![](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/images/placement-group-cluster.png)
* Places instances in the same AZ.
* Low latency, high throughput.
* Best to use single launch request. Adding instances may result in insufficient capacity error.
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

## Auto-Scaling Groups

![](https://docs.aws.amazon.com/autoscaling/ec2/userguide/images/sample-3-tier-architecture-with-azs-diagram.png)

* Can be created from a Launch Template or Configuration.
* Instance distribution
    * Amazon EC2 Auto Scaling attempts to distribute instances evenly between the Availability Zones that are enabled for your Auto Scaling group.
* Rebalancing
    * Availability Zone rebalancing
        *  The following actions can lead to rebalancing activity:
            * You change the Availability Zones for your group.
            * You explicitly terminate or detach instances and the group becomes unbalanced.
            * An Availability Zone that previously had insufficient capacity recovers and has additional capacity available.
            * An Availability Zone that previously had a Spot price above your maximum price now has a Spot price below your maximum price.
    * Capacity Rebalancing
        * When you turn on Capacity Rebalancing, Amazon EC2 Auto Scaling attempts to launch a Spot Instance whenever Amazon EC2 notifies that a Spot Instance is at an elevated risk of interruption.
* Scaling options:
    * Maintain current instance levels at all times.
        * Desired capacity = minimum capacity = maximum capacity.
    * Scale manually.
        * Increase desired and/or maximum capacity.
    * Predictive scaling
        * Predictive scaling builds a forecast based on historical data and scales out capacity in advance of forecasted hourly load, so that new instances are ready to handle traffic when the load arrives.
        * Based on target usage.
        * CPU utilisation, Network in (bytes), Network out (bytes), or Custom metric pair.
    * Dynamic scaling
        * A dynamic scaling policy instructs Amazon EC2 Auto Scaling to track a specific CloudWatch metric, and it defines what action to take when the associated CloudWatch alarm is in ALARM.
        * Target tracking scaling.
            * Based on target usage.
            * CPU utilisation, Network in (bytes), Network out (bytes), or Load balancer request count.
        * Step scaling.
            * Based on CloudWatch alarm.
            * Set to, Add, or Remove.
            * Can define multiple steps.
        * Simple scaling.
            * Based on CloudWatch alarm.
            * Set to, Add, or Remove.
    * Scheduled scaling.
        * Change desired, max, and min based on a schedule.
* Notifications
    * Can be sent to an SNS topics.
    * For the following events:
        * Launch
        * Terminate
        * Fail to launch
        * Fail to terminate
* Lifecyle Hooks
    * Lifecycle hooks enable an Auto Scaling group to be aware of events in the Auto Scaling instance lifecycle, and then perform a custom action when the corresponding lifecycle event occurs. A lifecycle hook provides a specified amount of time (one hour by default) to complete the custom action before the instance transitions to the next state.
### Launch Configuration 

* Note. AWS strongly recommend using Launch Templates instead of Launch Configurations.

* AMI
* Instance Type,
* Additional Configuration:
    * Request spot instances.
    * IAM profile
    * User data, etc.
* Storage
* Security groups
* Key pair (login)

### Launch Templates

* A launch template is similar to a launch configuration, in that it specifies instance configuration information. However, defining a launch template instead of a launch configuration allows you to have multiple versions of a launch template.

### AMIs

#### How tro copy to other regions
#### How to share across accounts
