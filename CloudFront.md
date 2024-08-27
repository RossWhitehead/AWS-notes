# CloudFront

![](https://d1.awsstatic.com/product-marketing/Cloudfront-cdn-diagram-v2.1a4a693fc371d29d794d318a01dfe1aecc4c658e.PNG)

* Global CDN.
* Content is cached at edge locations.
* Route53 directs traffic to edge locations close to the clients.

## Origins

* S3
* ELB
* Mediastore container
* Mediapackage container.

## Use Cases

* Accelerate static website content delivery (e.g. images, style sheets, and JavaScript)
    * S3 origin or a HTTP server
    * Can use Origin Access Identity (OAI) to easily restrict access to your S3 content.
* Serve video on demand or live streaming video.

## Edge Functions

* CloudFront functions or Lambda@Edge.
* Functions are assigned to the following behviours:
    * Viewer request
    * Viewer response
    * Origin request
    * Origin response.

## Price Class

* The price class determines which CloudFront edge locations serve your content.
    * All edge locations (best performance)
    * Only North America and Europe
    * North America, Europe, Asia, Middle East, and Africa.

## Restict access to S3 (Origin Access Identities)

* Create a special CloudFront user called an origin access identity (OAI) and associate it with your distribution.
* Configure your S3 bucket permissions so that CloudFront can use the OAI to access the files in your bucket and serve them to your users. Make sure that users can’t use a direct URL to the S3 bucket to access a file there.

## Restrict access to ALBs

* Configure CloudFront to add a custom HTTP header to requests that it sends to the Application Load Balancer.
* Configure the Application Load Balancer to only forward requests that contain the custom HTTP header.
* s(Optional) Require HTTPS to improve the security of this solution.
 


