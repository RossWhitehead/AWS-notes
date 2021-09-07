# Route53

## Domains

* Domains can be registered/transferred to Route53.

## Trusted Zones

* A hosted zone is a container that holds information about how you want to route traffic for a domain, such as example.com, and its subdomains.
* Can be public or private.
* Each hosted zone has 1 or more Records defining how traffic should be routed. 
    * A records can be routed to a IP addresses or aliased to:
        * API Gateway API
        * NLB, ALB, or Classic Load balancer
        * S3 Website Endpoint
        * Global Accelerator
        * CloudFront Distribution
        * Elastic Beanstalk Environment
        * VPC Endpoint.

## Routing Policy

* Simple: Simple records use standard DNS functionality.
* Weighted: Weighted records let you specify what portion of traffic to send to each resource.
* Geolocation: Geolocation records let you route traffic to your resources based on the geographic location of your users.
* Latency: Latency records let you route traffic to resources in the AWS Region that provides the lowest latency. All resources must be in AWS Regions.
* Failover: Failover records let you route traffic to a resource when the resource is healthy or to a different resource when the first resource is unhealthy.
* Multivalue answer: Multivalue answer records let you configure Route 53 to return multiple values, such as IP addresses for your web servers, in response to DNS queries.

## Resolvers

## Health Checks

## Traffic Flow Policies



