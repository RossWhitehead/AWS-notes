# API Gateway

* To build RESTful APIs, you can use either HTTP APIs or REST APIs from API Gateway. REST APIs offer a wide variety of features for building and managing RESTful APIs. HTTP APIs are up to 71% cheaper compared to REST APIs, but offer only API proxy functionality. HTTP APIs are optimized for performance—they offer the core functionality of API Gateway at a lower price.
* API Endpoint Types:
    * Regional
    * Edge Optimized (CloudFront)
    * Private.
* Deployments and Stages
    * Deployments expose APIs to users.
    * Deployments are associated with stages (e.g. Dev, Prod).
    * Stage varianles can be used to configure integrations and other config settings.
    * Changes to an API must be deployed to a stage to be visible.
    * Deployments can be rolled back.


## REST API

* Resource based API.
* Gateway responses can be customized (e.g. Default 4xx or 5xx).
* Resources
    * A REST API can have multiple resources.
* Methods
    * Each resource can have 1 or more HTTP methods (ANY, DELETE, GET, HEAD, OPTIONS, PATCH, POST, PUT).
* Method Execution Phases
    * Method Request, Integration Request, Integration Response, Method Response.
* Integration types
    * Lamdba function
    * HTTP
        * Existing HTTP endpoint.
    * Mock
        * Return a response using API Gateway mappings and transformations.
    * AWS Service
        * Most services including S3, SNS, SQS, CodePipeline, DynamoDB, Kinesis.
    * VPC Link
* Request and Response transformation.
* Access control through
    * Authorizers
        * IAM, Lambda or Cognito.
    * Resource policies.
    * Throttling
        * Account level, All methods in stage, All methods in usage plan, Mthods in usage plan, All requests from API key (quota)
    * Quotas
        * Limit requests by day, week, month per API key.
    * Usage plans.
        * Help meter API usage by key.
        * Throttling and quotas.
        * Associated with a API's stage.
        * API keys are added to the plan.
        * Resources/methods need to have "API Required" set to true.
    * WAF
        * A WAF Web ACL can be associated with a API's stage.
* API Keys.
* Client Certs.
* Stages
    * Settings for:
        * Enable API cache
        * Throttling
        * WAF
        * Canarys

## HTTP API

* HTTP APIs are designed for low-latency, cost-effective integrations with AWS services, including AWS Lambda, and HTTP endpoints. HTTP APIs support OIDC and OAuth 2.0 authorization, and come with built-in support for CORS and automatic deployments.
* Route based API
* Integration types
    * Lamdba function
    * HTTP URI
    * Private resource
        * ALB/NLB or AWS Cloud Map
        * ALB/NLB require the creation of a VPC Link.
    * EventBridge
    * SQS
    * AppConfig
    * Kinesis Data Streams
    * Step Functions
* Authorizers
    * JWT or Lambda.
* CORS can be set fo an API.
* Throttling can be set for each route.

## WebSocket API

## API Gateway EKS Integration

![](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2021/04/06/image-30.jpg)

* VPC Link private integration to a NLB.
* A NLB is created for each K8s service of type Loadbalancer. This coculd get costly,
* As an alternative create a ingress resource and use the AWS Load Balancer Controller to create a ALB.
    * For a REST API, we still need a NLB, and a target group should be created for the NLB that contains the IP addresses of the ALB instances (1 per zone) ENIs.
    * A HTTP API can be integrated directly with a ALB, but not needing the NLB.

## Accessing Private APIs

* Use PrivateLink.
