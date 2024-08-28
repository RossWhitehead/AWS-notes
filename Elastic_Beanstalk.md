# Elastic Beanstalk

With Elastic Beanstalk you can quickly deploy and manage applications in the AWS Cloud without having to learn about the infrastructure that runs those applications.

You simply upload your application, and Elastic Beanstalk automatically handles the details of capacity provisioning, load balancing, scaling, and application health monitoring.

You simply upload your application, and Elastic Beanstalk automatically handles the details of capacity provisioning, load balancing, scaling, and application health monitoring.

Elastic Beanstalk supports applications developed in: .NET, Go, Java, Node.js, PHP, Python, Ruby, Tomcat. Elastic Beanstalk also supports Docker platforms, enabling other languages.

## Concepts

* Application
    * Platform
        * e.g. Node.js, Docker, .NET Core, etc.
    * Branch
        * e.g. Node.js 14 running on 64bit Amazon Linux 2.
    * Platform version
        * e.g. 5.4.1.
    * Upload code from local file system ot public S3 bucket.
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

* Elastic Beanstalk dashboard allows the configuration for an environment to be changed.
    * Capacity
        * Auto-scaling group with load-balancing
        * Instance type
        * AMI
        * AZs
        * Scaling triggers
     
## Web server environments

![](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/images/aeb-architecture2.png)

* A web server environments consists of:
    * ELB
    * Auto-scaling group
    * One or more EC2 instances
    * A CNAME (URL) aliased in Route53 to the ELB
    * A Security Group for the EC2 instances

## Worker environments

![](https://docs.aws.amazon.com/images/elasticbeanstalk/latest/dg/images/aeb-architecture_worker.png)
