# Cloudfront

![](https://d1.awsstatic.com/product-marketing/Cloudfront-cdn-diagram-v2.1a4a693fc371d29d794d318a01dfe1aecc4c658e.PNG)

* Global CDN.
* Content is cached at edge locations.
* Route53 directs traffic to edge locations close to the clients.

## Origins:
    * S3, ELB, Mediastore container, Mediapackage container.

## Use cases

* Accelerate static website content delivery.
    * S3 origin.
    * Can use Origin Access Identity (OAI) to easily restrict access to your S3 content.
* Serve video on demand or live streaming video.
 


