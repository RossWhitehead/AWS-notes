# Networking

## IP Addressing

### Private IPv4 addresses and internal DNS hostnames
* Private IP addresses are not reachable over the internet.
* Each instance is allocate a primary private IPv4 address, and is given an internal DNS hostname that resolves to the primary private IPv4 address; e.g. ip-10-251-50-12.ec2.internal.
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

## ENIs
* Virtual network card
 