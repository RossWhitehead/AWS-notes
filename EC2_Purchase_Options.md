## On-Demamd
* Pay, by the second, for the instances that you launch.

## Savings Plans
* Reduce your Amazon EC2 costs by making a commitment to a consistent amount of usage, in USD per hour, for a term of 1 or 3 years.

## Reserved Instances
* Reduce your Amazon EC2 costs by making a commitment to a consistent instance configuration, including instance type and Region, for a term of 1 or 3 years.
* Payment Options:
    * All up-front
    * Partial up-front
    * No up-front
    * The more you pay up-front the bigger the saving. 

## Spot Instances
* Request unused EC2 instances, which can reduce your Amazon EC2 costs significantly.
* You specify the maximum price you are willing to pay per instance hour. 
* If you bid higher than the current Spot Price, your Spot Instance is launched and will be charged at the current Spot Price.
* Capacity that can be terminated by AWS if required elsewhere.
* Concepts
   * __Spot capacity pool__ – A set of unused EC2 instances with the same instance type (for example, m5.large) and Availability Zone.
   * __Spot price__ – The current price of a Spot Instance per hour.
   * __Spot Instance request__ – Requests a Spot Instance. When capacity is available, Amazon EC2 fulfills your request. A Spot Instance request is either one-time or persistent. Amazon EC2 automatically resubmits a persistent Spot Instance request after the Spot Instance associated with the request is interrupted.
   * __EC2 instance rebalance recommendation__ – Amazon EC2 emits an instance rebalance recommendation signal to notify you that a Spot Instance is at an elevated risk of interruption. This signal provides an opportunity to proactively rebalance your workloads across existing or new Spot Instances without having to wait for the two-minute Spot Instance interruption notice.
   * __Spot Instance interruption__ – Amazon EC2 terminates, stops, or hibernates your Spot Instance when Amazon EC2 needs the capacity back. Amazon EC2 provides a Spot Instance interruption notice, which gives the instance a two-minute warning before it is interrupted.

## Dedicated Hosts
Pay for a physical host that is fully dedicated to running your instances, and bring your existing per-socket, per-core, or per-VM software licenses to reduce costs.

## Dedicated Instances
* Pay, by the hour, for instances that run on single-tenant hardware.

## Capacity Reservations
* Reserve capacity for your EC2 instances in a specific Availability Zone for any duration.



