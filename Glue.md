# AWS Glue

* Fully managed ETL (extract, transform, and load) service that makes it simple and cost-effective to categorize your data, clean it, enrich it, and move it reliably between various data stores and data streams.
* Consists of:
    * a central metadata repository known as the AWS Glue Data Catalog, 
    * an ETL engine that automatically generates Python or Scala code, 
    * and a flexible scheduler that handles dependency resolution, job monitoring, and retries.
* Use cases:
![](https://s3.amazonaws.com/media.whizlabs.com/learn/2019/04/04/ckeditor_2.png)
* Q: When should I use AWS Glue vs. Amazon EMR?
    * AWS Glue works on top of the Apache Spark environment to provide a scale-out execution environment for your data transformation jobs. AWS Glue infers, evolves, and monitors your ETL jobs to greatly simplify the process of creating and maintaining jobs. Amazon EMR provides you with direct access to your Hadoop environment, affording you lower-level access and greater flexibility in using tools beyond Spark.

* Q: When should I use AWS Glue vs AWS Database Migration Service?

    * AWS Database Migration Service (DMS) helps you migrate databases to AWS easily and securely. For use cases which require a database migration from on-premises to AWS or database replication between on-premises sources and sources on AWS, we recommend you use AWS DMS. Once your data is in AWS, you can use AWS Glue to move, combine, replicate, and transform data from your data source into another database or data warehouse, such as Amazon Redshift.

* Q: When should I use AWS Glue vs AWS Batch?

    * AWS Batch enables you to easily and efficiently run any batch computing job on AWS regardless of the nature of the job. AWS Batch creates and manages the compute resources in your AWS account, giving you full control and visibility into the resources being used. AWS Glue is a fully-managed ETL service that provides a serverless Apache Spark environment to run your ETL jobs. For your ETL use cases, we recommend you explore using AWS Glue. For other batch-oriented use cases, including some ETL use cases, AWS Batch might be a better fit.

