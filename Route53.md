# Route53

Domain registration, DNS routing, and health checking.

## Hosted Zones

* A hosted zone is a container that holds information about how you want to route traffic for a domain, such as example.com, and its subdomains.
* Types: 
    * Public (how to route internet traffic to the domain)
    * Private (how to respond to DNS queries for a domain and its subdomains within one or more VPCs)
* To use a private hosted zone, the following VPC settings must be set to true:
    * enableDnsHpstnames - determines whether instances launched in the VPC receive public DNS hostnames that correspond to their public IP addresses.
    * enableDnsSupport (Resolution) - determines whether DNS resolution through the Amazon DNS server is supported for the VPC.
* Each hosted zone has records defining how traffic should be routed. 
    * NS (name server)
        * Identifies the four name servers that you give to your registrar or your DNS service so that DNS queries are routed to Route 53 name servers.
    * SOA (start of authority)
        * Identifies the based DNS infor for the domain. 
    * A 
        * Routes traffic to IPv4 addresses or aliases AWS services such as API Gateway, Load Balancers, S3 Website Endpoints, and VPC Endpoints.
        * e.g. Route internet traffic for example.com to the IP address of a host in your data center.
    * AAAA 
        * Routes traffic to IPv6 addresses.
    * CNAME
        * Routes traffic to another domain name. 
        * e.g. Route traffic for a subdomain called operations.tokyo.example.com to the IP address of a different host.
    * MX
        * Specifies mail servers
        * e.g. Route email for that domain (ichiro@example.com) to a mail server (mail.example.com).  

## Routing Policy

Determines how Route53 responds to queries.

* Simple
    * Simple routing routes traffic to a single resource,
    * If you specifiy multiple values (IP addresses or aliases) all values are returned to the client in random order. The client can then choose the value and submit the query.
* Failover
    * Failover routing routes traffic to a "Primary" resource when the resource is healthy or to a "Secondary" resource when the first resource is unhealthy.
    * Requires the creation of 2 records with the same subdomain, Primary and Secondary.
* Geolocation
    * Geolocation routing routes traffic to your resources based on the geographic location of your users.
    * You can use it to localize content or restrict delivery to certain regions.
    * Requires the creation of multiple records, 1 per continent country or state (US-only).
    * Traffic from IP addresses that are not mapped to locations or from IP addresses that do not have a geolocation record are handled by the "Default" record. 
* Geoproximity
    * Geoproximity routiong route traffic based on the geographic proximity the users and resources.
    * Requires the creation of Route53 Traffic Flow policies.
* Latency
    * Latency routing routes traffic to resources in the AWS Region that provides the lowest latency. All resources must be in AWS Regions.
    * Requires the creation of multiple records, 1 for each of the regions where your resources are located.
    * Route53 determines which region gives the user the lowest latency, and then selects a latency record for that region.
* Multivalue Answer 
    * Multivalue answer routing returns multiple values, such as IP addresses for your web servers
    * You can specify multiple values for almost any record, but multivalue answer routing also lets you check the health of each resource, so Route 53 returns only values for healthy resources. 
* Weighted
    * Weighted routing routes lets you specify what portion of traffic to send to each resource.
    * Can be used for testing.

## Resolvers

## Health Checks

## Traffic Flow Policies

## Metrics

Route53 sends metrics to CloudWatch in the number of DNS queries for a public hosted zone.



