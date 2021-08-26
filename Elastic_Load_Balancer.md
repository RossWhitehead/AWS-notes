# Elastic Load Balancer

* Distributes incoming traffic across multiple targets.
* Monitors the health of its registered targets, and routes traffic only to the healthy targets.
* Elastically scales to accomodate changing volume of traffic.
* Can be an internal load balancer or an internet-facing load balancer.


## Availability Zones and load balancer nodes

* When you enable a AZ for a load balancer, a load balancer node is created in the AZ.
* If you register targets in an Availability Zone but do not enable the Availability Zone, these registered targets do not receive traffic.
* An ALB is required to have 2 or more enabled AZs.

### Cross-zone load balancing

![](https://docs.aws.amazon.com/elasticloadbalancing/latest/userguide/images/cross_zone_load_balancing_enabled.png)

* Clients send requests, and Amazon Route 53 responds to each request with the IP address of one of the load balancer nodes. This distributes traffic such that each load balancer node receives 50% of the traffic from the clients. Each load balancer node distributes its share of the traffic across the registered targets in its scope.

* If cross-zone load balancing is enabled, each of the 10 targets receives 10% of the traffic. This is because each load balancer node can route its 50% of the client traffic to all 10 targets.

* Cross-zone load balancing is always enabled for ALBs, and disbled by default for NLBs and GLBs.

## Application Load Balancers

![](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/images/component_architecture.png)

* Support following protocols on front-end connections: HTTP/0.9, HTTP/1.0, HTTP/1.1, HTTP/2.
* Also supports HTTP to WebSockets connection upgrades.
* Uses HTTP/1.1 on backend connections (load balancer to registered target) by default. However, you can use the protocol version to send the request to the targets using HTTP/2 or gRPC.
* Automatically add X-Forwarded-For, X-Forwarded-Proto, and X-Forwarded-Port headers to the request.

### Listeners

* You add one or more listeners to your load balancer.
* A listener checks for connection requests from clients, using the protocol and port that you configure. 
* The rules that you define for a listener determine how the load balancer routes requests to its registered targets. 
* Each rule consists of a priority, one or more actions, and one or more conditions. 
* When the conditions for a rule are met, then its actions are performed. 
* You must define a default rule for each listener, and you can optionally define additional rules.

### Target Groups

* Each target group routes requests to one or more registered targets, such as EC2 instances, using the protocol and port number that you specify. 
* You can register a target with multiple target groups. 
* You can configure health checks on a per target group basis. Health checks are performed on all targets registered to a target group that is specified in a listener rule for your load balancer.
