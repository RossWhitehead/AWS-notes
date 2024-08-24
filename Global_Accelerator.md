 # AWS Global Accelerator

 * Fully managed global network traffic manager
 * AWS Global Accelerator is a networking service that sends your user’s internet traffic through AWS’s global network infrastructure, improving your internet user performance by up to 60%. 
 * It also makes it easier to operate multi-regional deployments by providing you with two static IPs that are anycast from AWS’s globally distributed edge locations, giving you a single entry point to your application regardless of how many AWS Regions it’s deployed in. 
 * Instead of relying on DNS for routing traffic at a global level (which is often problematic if you’re dealing with clients that cache DNS results), Global Accelerator can switch traffic routes without requiring DNS changes, or delays caused by DNS propagation and client-side caching.

## Benefits
* Helps create a more robust architecture
* Increases network stability
* Provides automatic health checking a routing
* Avoids delays related to DNS propogation and client-side DNS caching

 ![](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2020/12/05/image-10.jpg)

 https://aws.amazon.com/blogs/containers/operating-a-multi-regional-stateless-application-using-amazon-eks/
