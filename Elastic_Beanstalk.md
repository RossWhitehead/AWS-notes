# Elastic Beanstalk
TODO: Needs updating.

![](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/images/aeb-architecture2.png)
## Concepts
* Application
    * Platform
        * e.g. Node.js, Docker, .NET Core, etc.
    * Branch
        * e.g. Node.js 14 running on 64bit Amazon Linux 2.
    * Platform version
        * e.g. 5.4.1.
    * Upload code from local file system ot pblic S3 bucket.
* Environment
    * Each application has 1 or more environments (e.g. dev, test, prod).
* Version
    * New versions can be uploaded and deployed to an environment
    * Deployment policies
        * All at once
        * Rolling
        * Rolling with additional batch
        * Immutable
## Architecture
* The following gets automatically provisoned:
    * EC2
    * S3
    * ENI
    * Security group
    * Load balancer and auto-scalling group (optional)
* Elastic Beanstalk dashboard allows the configuration for an environment to be changed.
    * Capacity
        * Auto-scaling group with load-balancing
        * Instance type
        * AMI
        * AZs
        * Scaling triggers
