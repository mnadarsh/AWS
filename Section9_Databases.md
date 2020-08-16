# Databases Intro

    • Storing data on disk (EFS, EBS, EC2 Instance Store, S3) can have its limits.
    • Sometimes, you want to store data in a database…
    • You can structure the data.
    • You build indexes to efficiently query / search through the data.
    • You define relationships between your datasets.
    • Databases are optimized for a purpose and come with different features, shapes and constraints.
 
 **Relational Databases**
  
    • Looks just like Excel spreadsheets, with links between them!
    • Can use the SQL language to perform queries / lookups.
    
 **NoSQL Databases*
 
    • NoSQL = non-SQL = non relational databases.
    • NoSQL databases are purpose built for specific data models and have flexible schemas for building modern applications.
    • Benefits:
      • Flexibility: easy to evolve data model.
      • Scalability: designed to scale-out by using distributed clusters.
      • High-performance: optimized for a specific data model.
      • Highly functional: types optimized for the data model.
      • Examples: Key-value, document, graph, in-memory, search databases.
      
 **NoSQL data example: JSON**
 
      • JSON = JavaScript Object Notation.
      • JSON is a common form of data that fits into a NoSQL model.
      • Data can be nested.
      • Fields can change over time.
      • Support for new types: arrays, etc…
      
      {
        "name": "John",
        "age": 30,
        "cars": [
        "Ford",
        "BMW",
        "Fiat"
        ],
        "address": {
        "type": "house",
        "number": 23,
        "street": "Dream Road"
          }
      }
      
  **Databases & Shared Responsibility on AWS**
  
      AWS
      
          • AWS offers use to manage different databases.
          • Benefits include:
                • Quick Provisioning, High Availability, Vertical and Horizontal Scaling
                • Automated Backup & Restore, Operations, Upgrades
                • Operating System Patching is handled by AWS
                • Monitoring, alerting
          • Note: many databases technologies could be run on EC2, but you must handle yourself 
                  the resiliency, backup, patching, high availability, fault tolerance, scaling…
   
  **AWS RDS Overview**
  
      • RDS stands for Relational Database Service.
      • It’s a managed DB service for DB use SQL as a query language.
      • It allows you to create databases in the cloud that are managed by AWS.
          • Postgres
          • MySQL
          • MariaDB
          • Oracle
          • Microsoft SQL Server
          • Aurora (AWS Proprietary database)
          
   **Advantage over using RDS versus deploying DB on EC2**
   
      • RDS is a managed service:
          • Automated provisioning, OS patching
          • Continuous backups and restore to specific timestamp (Point in Time Restore)!
          • Monitoring dashboards
          • Read replicas for improved read performance
          • Multi AZ setup for DR (Disaster Recovery)
          • Maintenance windows for upgrades
          • Scaling capability (vertical and horizontal)
          • Storage backed by EBS (gp2 or io1)
      • BUT you can’t SSH into your instances
      
      
 ![RDS Architecture](https://github.com/mnadarsh/AWS/blob/master/RDS_Architecture.PNG "RDS Architecure")
  
   **Amazon Aurora**
    
    • Aurora is a proprietary technology from AWS (not open sourced).
    • PostgreSQL and MySQL are both supported as Aurora DB.
    • Aurora is “AWS cloud optimized” and claims 5x performance improvement over MySQL on RDS,
      over 3x performance of Postgres on RDS.
    • Aurora storage automatically grows in increments of 10GB, up to 64 TB.
    • Aurora costs more than RDS (20% more) – but is more efficient.
    • Not in the free tier
          
   **Amazon ElastiCache**
   
    • The same way RDS is to get managed Relational Databases…
    • ElastiCache is to get managed Redis or Memcached.
    • Caches are in-memory databases with high performance, low latency.
    • Helps reduce load off databases for read intensive workloads.
    • AWS takes care of OS maintenance / patching, optimizations, setup, configuration, monitoring,
      failure recovery and backups.
    
   ![Elastic_cache](https://github.com/mnadarsh/AWS/blob/master/Elastic_Cache.PNG "Elastic_Cache")
   
  **DynamoDB**
  
    • Fully Managed Highly available with replication across 3 AZ.
    • NoSQL database - not a relational database.
    • Scales to massive workloads, distributed “serverless” database.
    • Millions of requests per seconds, trillions of row, 100s of TB of storage.
    • Fast and consistent in performance.
    • Single-digit millisecond latency – low latency retrieval.
    • Integrated with IAM for security, authorization and administration.
    • Low cost and auto scaling capabilities.
   
  ![Dynamo_DB](https://github.com/mnadarsh/AWS/blob/master/DynamoDB.PNG "Dynamo_DB")
   
  **Redshift Overview**
  
    • Redshift is based on PostgreSQL, but it’s not used for OLTP.
    • It’s OLAP – online analytical processing (analytics and data warehousing).
    • Load data once every hour, not every second.
    • 10x better performance than other data warehouses, scale to PBs of data.
    • Columnar storage of data (instead of row based).
    • Massively Parallel Query Execution (MPP), highly available.
    • Pay as you go based on the instances provisioned.
    • Has a SQL interface for performing the queries.
    • BI tools such as AWS Quicksight or Tableau integrate with it .
    
  **Amazon EMR**
  
    • EMR stands for “Elastic MapReduce”.
    • EMR helps creating Hadoop clusters (Big Data) to analyze and process vast amount of data.
    • The clusters can be made of hundreds of EC2 instances.
    • Also supports Apache Spark, HBase, Presto, Flink…
    • EMR takes care of all the provisioning and configuration.
    • Auto-scaling and integrated with Spot instances.
    • Use cases: data processing, machine learning, web indexing, big data…
    
  **Athena Overview**
  
    • Fully Serverless database with SQL capabilities.
    • Used to query data in S3.
    • Pay per query.
    • Output results back to S3.
    • Secured through IAM.
    • Use Case: one-time SQL queries, serverless queries on S3, log analytics.
    
  **AWS Glue**
  
    • Managed extract, transform, and load (ETL) service.
    • Useful to prepare and transform data for analytics.
    • Fully serverless service.
    • Glue Data Catalog: catalog of datasets
    • can be used by Athena, Redshift, EMR.
    
  ![AWS_Glue](https://github.com/mnadarsh/AWS/blob/master/AWS_Glue.PNG "AWS_Glue")  
  
 **DMS – Database Migration Service**
  
    • Quickly and securely migrate databases to AWS, resilient, self healing.
    • The source database remains available during the migration.
    • Supports:
        • Homogeneous migrations: ex Oracle to Oracle
        • Heterogeneous migrations: ex Microsoft SQL Server to Aurora.
    
 **Databases & Analytics Summary in AWS**
 
    • Relational Databases - OLTP: RDS & Aurora (SQL).
    • In-memory Database: ElastiCache.
    • Key/Value Database: DynamoDB (serverless).
    • Warehouse - OLAP: Redshift (SQL).
    • Hadoop Cluster: EMR.
    • Athena: query data on Amazon S3 (serverless & SQL).
    • Glue: Managed ETL (Extract Transform Load) and Data Catalog service.
    • Database Migration: DMS.
