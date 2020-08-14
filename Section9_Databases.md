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
      
          
    
