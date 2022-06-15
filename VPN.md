# VPN

![](https://docs.aws.amazon.com/vpn/latest/s2svpn/images/vpn-basic-diagram.png)

![](https://docs.aws.amazon.com/vpn/latest/s2svpn/images/site-site-transit-gateway-basic.png)

* Customer Gateway
    * A customer gateway is a resource that you create in AWS that represents the customer gateway device in your on-premises network. 
* Customer Gateway Device
    * A customer gateway device is a physical device or software application on your side of the Site-to-Site VPN connection. 
* Virtual Private Gateway / Transit Gateway
    * The Customer Gateway Devize is connected via VPN to either a Virtual Private Gateway (single-VPC) or a Transit Gateway (multiple VPCs)
* Each Site-to-Site VPN has 2 tunnels for redundancy.
