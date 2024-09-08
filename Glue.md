# AWS Glue

Fully managed serverless ETL (extract, transform, and load) service 

Consists of:
* ETL jobs
   * Multiple data sources, including S3, DynamoDB, and RDS
   * Build ETL jobs using Python Shell, Glue Streaming, and Cloud Studio
   * Choice of engines: Spark and Ray 
* Data catalog
* Glue Studio
* Data quality
* DataBrew

![](https://docs.aws.amazon.com/images/glue/latest/dg/images/HowItWorks-overview.png)

Use cases:

* Q: When should I use AWS Glue vs. Amazon EMR?
    * AWS Glue works on top of the Apache Spark environment to provide a scale-out execution environment for your data transformation jobs. AWS Glue infers, evolves, and monitors your ETL jobs to greatly simplify the process of creating and maintaining jobs. Amazon EMR provides you with direct access to your Hadoop environment, affording you lower-level access and greater flexibility in using tools beyond Spark.

* Q: When should I use AWS Glue vs AWS Database Migration Service?

    * AWS Database Migration Service (DMS) helps you migrate databases to AWS easily and securely. For use cases which require a database migration from on-premises to AWS or database replication between on-premises sources and sources on AWS, we recommend you use AWS DMS. Once your data is in AWS, you can use AWS Glue to move, combine, replicate, and transform data from your data source into another database or data warehouse, such as Amazon Redshift.

* Q: When should I use AWS Glue vs AWS Batch?

    * AWS Batch enables you to easily and efficiently run any batch computing job on AWS regardless of the nature of the job. AWS Batch creates and manages the compute resources in your AWS account, giving you full control and visibility into the resources being used. AWS Glue is a fully-managed ETL service that provides a serverless Apache Spark environment to run your ETL jobs. For your ETL use cases, we recommend you explore using AWS Glue. For other batch-oriented use cases, including some ETL use cases, AWS Batch might be a better fit.

