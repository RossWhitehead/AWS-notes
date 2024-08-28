# Elastic Beanstalk

With Elastic Beanstalk you can quickly deploy and manage applications in the AWS Cloud without having to learn about the infrastructure that runs those applications.

You simply upload your application, and Elastic Beanstalk automatically handles the details of capacity provisioning, load balancing, scaling, and application health monitoring.

You simply upload your application, and Elastic Beanstalk automatically handles the details of capacity provisioning, load balancing, scaling, and application health monitoring.

Elastic Beanstalk supports applications developed in: .NET, Go, Java, Node.js, PHP, Python, Ruby, Tomcat. Elastic Beanstalk also supports Docker platforms, enabling other languages.

## Concepts

* Application
    * An Elastic Beanstalk application is a logical collection of Elastic Beanstalk components, including environments, versions, and environment configurations. In Elastic Beanstalk an application is conceptually similar to a folder. 
* Application version
    * In Elastic Beanstalk, an application version refers to a specific, labeled iteration of deployable code for a web application. An application version points to an Amazon Simple Storage Service (Amazon S3) object that contains the deployable code, such as a Java WAR file.    
* Environment
    * An environment is a collection of AWS resources running an application version. Each environment runs only one application version at a time, however, you can run the same application version or different application versions in many environments simultaneously. When you create an environment, Elastic Beanstalk provisions the resources needed to run the application version you specified.
* Environment tier
    * When you launch an Elastic Beanstalk environment, you first choose an environment tier. The environment tier designates the type of application that the environment runs, and determines what resources Elastic Beanstalk provisions to support it. An application that serves HTTP requests runs in a web server environment tier. A backend environment that pulls tasks from an Amazon Simple Queue Service (Amazon SQS) queue runs in a worker environment tier.  
* Platform
    * A platform is a combination of an operating system, programming language runtime, web server, application server, and Elastic Beanstalk components. You design and target your web application to a platform. Elastic Beanstalk provides a variety of platforms on which you can build your applications. 
          
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

* A web server environment consists of:
    * ELB
    * Auto-scaling group
    * One or more EC2 instances
    * A CNAME (URL) aliased in Route53 to the ELB
    * A Security Group for the EC2 instances

## Worker environments

![](https://docs.aws.amazon.com/images/elasticbeanstalk/latest/dg/images/aeb-architecture_worker.png)

* A worker enviornment consists of:
    * an Auto Scaling group,
    * one or more EC2 instances,
    * an IAM role.
    * an SQS queue
* When you launch a worker environment, Elastic Beanstalk installs the necessary support files for your programming language of choice and a daemon on each EC2 instance in the Auto Scaling group. The daemon reads messages from an Amazon SQS queue. The daemon sends data from each message that it reads to the web application running in the worker environment for processing. If you have multiple instances in your worker environment, each instance has its own daemon, but they all read from the same Amazon SQS queue.  
