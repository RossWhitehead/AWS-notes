# CloudWatch

Monitoring for AWS resources and application. 

![](https://docs.aws.amazon.com/images/AmazonCloudWatch/latest/monitoring/images/CW-Overview.png)

## Cloudwatch Alarms

* Watch a single metric over a specified time period, and performs one or more specified actions, based on the value of the metric relative to a threshold. * The action is 
    * a notification sent to an Amazon SNS topic, 
    * an EC2 actions (stop, terminate, reboot, recover),
    * an EC2 Auto Scaling policy,
    * create OpsItems in Systems Manager Ops Center,
    * or create incidents in AWS Systems Manager Incident Manager. 

## e.g. Create metrics from logs

* Create a lambda function 
* The "Create a new role with basic Lambda permissions" by default gives the function permissions to uoload logs to CloudWatch.
* A log group is created in CloudWatch.
* Create a metrics filter for the log group.
* Assign a metric to the metrics filter.
* Create an alarm based on the metric.
