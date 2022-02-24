# Networking

## VPCs and subnets

### DNS Hostnames and DNS Resolution

* DNS Hostnames:
    * Determines whether the VPC supports assigning public DNS hostnames to instances with public IP addresses.
    * Defaults to enabled for default VPC and disabled for additional VPCs.
* DNS Resolution (DNS support):
    * Determines whether the VPC supports DNS resolution through the Amazon provided DNS server (Amazon Route 53 Resolver server)
    * Defaults to enabled.

![](https://docs.aws.amazon.com/vpc/latest/userguide/images/subnets-diagram.png)

* Public subnet: 
    * The subnet's IPv4 or IPv6 traffic is routed to an internet gateway or an egress-only internet gateway and can reach the public internet.
    * If you have an EC2 instance launched into a public subnet and you want the instance to communicate with the internet, it must have a public IPv4 address (or an Elastic IP address) or an IPv6 address. 
* Private subnet: The subnet’s IPv4 or IPv6 traffic is not routed to an internet gateway or egress-only internet gateway and cannot reach the public internet.
* VPN-only subnet: The subnet doesn't have a route to the internet gateway, but it has its traffic routed to a virtual private gateway for a Site-to-Site VPN connection. Currently, does not support IPv6 traffic over a Site-to-Site VPN connection.

## IP Addressing

The first four IP addresses and the last IP address in each subnet CIDR block are not available for you to use, and cannot be assigned to an instance. For example, in a subnet with CIDR block 10.0.0.0/24, the following five IP addresses are reserved:

* 10.0.0.0: Network address.
* 10.0.0.1: Reserved by AWS for the VPC router.
* 10.0.0.2: Reserved by AWS. The IP address of the DNS server is the base of the VPC network range plus two. For VPCs with multiple CIDR blocks, the IP address of the DNS server is located in the primary CIDR. We also reserve the base of each subnet range plus two for all CIDR blocks in the VPC. For more information, see Amazon DNS server.
* 10.0.0.3: Reserved by AWS for future use.
* 10.0.0.255: Network broadcast address. We do not support broadcast in a VPC, therefore we reserve this address.


### Private IPv4 addresses and internal DNS hostnames
* Private IP addresses are not reachable over the internet.
* Each instance is allocated a primary private IPv4 address, and is given an internal DNS hostname that resolves to the primary private IPv4 address; e.g. ip-10-251-50-12.ec2.internal.
* Each instance has a default network interface (eth0) that is assigned the primary private IPv4 address.
* Multiple secondary private IPv4 and IPv6 addresses can be assigned to a network interface.

### Public IPv4 addresses and external DNS hostnames
* Public IPv4 addresses are reachable over the internet.
* Each instance that receives a public IP address is also given an external DNS hostname; for example, ec2-203-0-113-25.compute-1.amazonaws.com.
* When you launch an instance in a default VPC, we assign it a public IP address by default. When you launch an instance into a nondefault VPC, the subnet has an attribute that determines whether instances launched into that subnet receive a public IP address from the public IPv4 address pool. By default, we don't assign a public IP address to instances launched in a nondefault subnet.
* We release your instance's public IP address when it is stopped, hibernated, or terminated. Your stopped or hibernated instance receives a new public IP address when it is started.
* We release your instance's public IP address when you associate an Elastic IP address with it. When you disassociate the Elastic IP address from your instance, it receives a new public IP address.
* If the public IP address of your instance in a VPC has been released, it will not receive a new one if there is more than one network interface attached to your instance.
* If your instance's public IP address is released while it has a secondary private IP address that is associated with an Elastic IP address, the instance does not receive a new public IP address.
* If you require a persistent public IP address that can be associated to and from instances as you require, use an Elastic IP address instead.

### Elastic IP addresses (IPv4)
* An Elastic IP address is a public IPv4 address that you can allocate to your account. You can associate it to and disassociate it from instances as you require. It's allocated to your account until you choose to release it.

### IPv6
* Optional.
* IPv6 CIDR block is automatically assigned.
* Globally unique and reachable over the internet.
* VPC and subnet sizing for IPv6 = /56 and /64.

## Routing

* A VPC has a primary and optionally multiple secondary CIDR block associations. For each CIDR block a route is automatically added to the VPC route tables to enable routing within the VPC.

| Destination | Target |
| ----------- | ------ |
| 10.0.0.0/16 | local |


## ENIs
* Virtual network card

## VPC-Peering

![](https://docs.aws.amazon.com/vpc/latest/peering/images/peering-intro-diagram.png)

* A VPC peering connection is a networking connection between two VPCs that enables you to route traffic between them using private IPv4 addresses or IPv6 addresses.
* Can be created for VPCs within different account or regions.
* Requires non-overlapping CIDR ranges.
* VPC Peering connections are not transitive.

Steps to create a VPC Peering connction:
1. Owner of the requester VPC sends a request to the owner of the accepter VPC.
2. Owner of the accepter VPC accepts the VPC peering connection.
3. For each VPC, add a route to one or more VPC route tables that points to the IP address range of the other VPC with the target being the VPC connection. 
4. If required, update the security group rules that are associated with your instance to ensure that traffic to and from the peer VPC is not restricted.
5. Enable DNS Resolution for your VPC connection. After enabling DNS resolution, if instances on either side of the VPC peering connection address each other using a public DNS hostname, the hostname resolves to the private IP address of the instance.

## PrivateLink

![](https://docs.aws.amazon.com/whitepapers/latest/aws-vpc-connectivity-options/images/image20.png)

* Private connectivity from VPCs to AWS hosted services.
* Uses private IP addresses and security groups within an Amazon VPC so that services function as though they were hosted directly within an Amazon VPC.
* Uses Network Load Balancers to connect interface endpoints to services.

### VPC Endpoint

* The entry point in your VPC that enables you to connect privately to a service.
* A VPC Endpoint creates an elastic network interface in each subnet with a private IP address that serves as an entry point for traffic destined to the service.

#### Interface Endpoint

* An elastic network interface with a private IP address from the IP address range of your subnet.
* Serves as an entry point for traffic destined to a supported AWS service or a VPC endpoint service.

#### Gateway Load Balancer Endpoint

* Entry point to intercept traffic and route it to a service that you've configured using Gateway Load Balancers.

#### Gateway Endpoint

* For DynamoDB and S3.
* Targets specific IP routes in an Amazon VPC route table, in the form of a prefix-list.
Service (Amazon S3). 
* Gateway endpoints do not enable AWS PrivateLink


### Endpoint service

* Your own application or service in your VPC. Other AWS principals can create an endpoint from their VPC to your endpoint service.




 
