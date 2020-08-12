# Amazon S3

  **Introduction**

      • Amazon S3 is one of the main building blocks of AWS.
      • It’s advertised as ”infinitely scaling” storage.
      • Many websites use Amazon S3 as a backbone.
      • Many AWS services uses Amazon S3 as an integration as well.
      • We’ll have a step-by-step approach to S3.
      • The CCP exam requires “deeper” knowledge about S3.
  
  **S3 Use cases**
  
      • Backup and storage
      • Disaster Recovery
      • Archive
      • Hybrid Cloud storage
      • Application hosting
      • Media hosting
      • Data lakes & big data analytics
      • Software delivery
      • Static website
  
  **Amazon S3 Overview - Buckets**

      • Amazon S3 allows people to store objects (files) in “buckets” (directories).
      • Buckets must have a globally unique name (across all regions all accounts).
      • Buckets are defined at the region level.
      • S3 looks like a global service but buckets are created in a region.
      • Naming convention
          • No uppercase
          • No underscore
          • 3-63 characters long
          • Not an IP
          • Must start with lowercase letter or number
      
  **Amazon S3 Overview - Objects**

       • Objects (files) have a Key.
       • The key is the FULL path:
          • s3://my-bucket/my_file.txt
          • s3://my-bucket/my_folder1/another_folder/my_file.txt
       • The key is composed of **prefix** + *object name*
          • s3://my-bucket/**my_folder1/another_folder**/*my_file.txt*
       • There’s no concept of “directories” within buckets(although the UI will trick you to think otherwise)
       • Just keys with very long names that contain slashes (“/”)
       
       • Object values are the content of the body:
          • Max Object Size is 5TB (5000GB)
          • If uploading more than 5GB, must use “multi-part upload”.
          
       • Metadata (list of text key / value pairs – system or user metadata)
       • Tags (Unicode key / value pair – up to 10) – useful for security / lifecycle
       • Version ID (if versioning is enabled).
       
  **S3 Security**
  
      • User based
        • IAM policies - which API calls should be allowed for a specific user from IAM console
      • Resource Based
        • Bucket Policies - bucket wide rules from the S3 console - allows cross account
        • Object Access Control List (ACL) – finer grain
        • Bucket Access Control List (ACL) – less common
      • Note: an IAM principal can access an S3 object if
        • the user IAM permissions allow it OR the resource policy ALLOWS it
        • AND there’s no explicit DENY
      • Encryption: encrypt objects in Amazon S3 using encryption keys

  **Amazon S3 - Versioning**
  
    • You can version your files in Amazon S3.
    • It is enabled at the bucket level.
    • Same key overwrite will increment the “version”: 1, 2, 3….
    • It is best practice to version your buckets
        • Protect against unintended deletes (ability to restore a version).
        • Easy roll back to previous version.
    • Notes:
        • Any file that is not versioned prior to enabling versioning will have version “null”.
        • Suspending versioning does not delete the previous versions.
   
  **S3 Access Logs**
  
    • For audit purpose, you may want to log all access to S3 buckets.
    • Any request made to S3, from any account, authorized or denied, will be logged into another S3 bucket.
    • That data can be analyzed using data analysis tools…
    • Very helpful to come down to the root cause of an issue, or audit usage, view suspicious patterns, etc…
  
  **S3 Replication (CRR & SRR)**
  
    • Must enable versioning in source and destination.
    • Cross Region Replication (CRR).
    • Same Region Replication (SRR).
    • Buckets can be in different accounts.
    • Copying is asynchronous.
    • Must give proper IAM permissions to S3.
    • CRR - Use cases: compliance, lower latency access, replication across accounts.
    • SRR – Use cases: log aggregation, live replication between production and test accounts.

  **S3 Storage Classes**
  
    • Amazon S3 Standard - General Purpose
    • Amazon S3 Standard-Infrequent Access (IA)
    • Amazon S3 One Zone-Infrequent Access
    • Amazon S3 Intelligent Tiering
    • Amazon Glacier
    • Amazon Glacier Deep Archive
    • Amazon S3 Reduced Redundancy Storage (deprecated - omitted)
    
  **S3 Durability and Availability**
  
    • Durability:
        • High durability (99.999999999%, 11 9’s) of objects across multiple AZ
        • If you store 10,000,000 objects with Amazon S3, you can on average expect to incur a loss of a single object once every 10,000 years.
        • Same for all storage classes
    • Availability:
         • Measures how readily available a service is
         • S3 standard has 99.99% availability, which means it will not be available 53 minutes a year
         • Varies depending on storage class
         
  **S3 Standard – General Purposes**
  
      • 99.99% Availability
      • Used for frequently accessed data
      • Low latency and high throughput
      • Sustain 2 concurrent facility failures
      • Use Cases: Big Data analytics, mobile & gaming applications, content distribution…
  
  **S3 Standard – Infrequent Access (IA)**
  
      • Suitable for data that is less frequently accessed, but requires rapid access when needed.
      • 99.9% Availability.
      • Lower cost compared to Amazon S3 Standard, but retrieval fee.
      • Sustain 2 concurrent facility failures.
      • Use Cases: As a data store for disaster recovery, backups…
      
  **S3 Intelligent-Tiering**
  
      • 99.9% Availability.
      • Same low latency and high throughput performance of S3 Standard.
      • Cost-optimized by automatically moving objects between two access tiers based on changing access patterns:
          • Frequent access
          • Infrequent access
      • Resilient against events that impact an entire Availability Zone.
      
  **S3 One Zone - Infrequent Access (IA)**
   
      • Same as IA but data is stored in a single AZ.
      • 99.5% Availability.
      • Low latency and high throughput performance.
      • Lower cost compared to S3-IA (by 20%)
      • Use Cases: Storing secondary backup copies of on-premise data, or storing data you can recreate.
      
  **Amazon Glacier & Glacier Deep Archive**
  
      • Low cost object storage (in GB/month) meant for archiving / backup.
      • Data is retained for the longer term (years).
      • Various retrieval options of time + fees for retrieval:
      
            • Amazon Glacier – cheap:
                 • Expedited (1 to 5 minutes)
                 • Standard (3 to 5 hours)
                 • Bulk (5 to 12 hours)
                 
            • Amazon Glacier Deep Archive – cheapest:
                 • Standard (12 hours)
                 • Bulk (48 hours)
                 
  **Shared Responsibility Model for S3**
  
      AWS
      
          • Infrastructure (global security, durability, availability, sustain concurrent loss of data in two facilities)
          • Configuration and vulnerability analysis
          • Compliance validation
          
      User
      
           • S3 Versioning
           • S3 Bucket Policies
           • S3 Replication Setup
           • Logging and Monitoring
           • S3 Storage Classes
           • Data encryption at rest and in transit
           
 **Snowball**
 
        • Physical data transport solution that helps moving TBs or PBs of data in or out of AWS
        • Alternative to moving data over the network (and paying network fees)
        • Pay per data transfer job
        • Use cases: large data cloud migrations, DC decommission, disaster recovery
        • If it takes more than a week to transfer over the network, use Snowball devices!
        
 **Snowball Process**
 
      1. Request snowball devices from the AWS console for delivery.
      2. Install the snowball client on your servers.
      3. Connect the snowball to your servers and copy files using the client.
      4. Ship back the device when you’re done (goes to the right AWS facility)
      5. Data will be loaded into an S3 bucket.
      6. Snowball is completely wiped.
      
 **Snowball Edge**
 
      • Snowball Edges (100 TB) add computational capability to the device.
      • Supports a custom EC2 AMI so you can perform processing on the go.
      • Supports custom Lambda functions.
      • Very useful to pre-process the data while moving.
      • Use case: data migration, image collation, IoT capture, machine learning
      • “Snowball” is deprecated in favor of “Snowball Edge”
      
**AWS Snowmobile**

      • Transfer exabytes of data (1 EB = 1,000 PB = 1,000,000 TBs)
      • Each Snowmobile has 100 PB of capacity (use multiple in parallel)
      • Better than Snowball if you transfer more than 10 PB.
      
**Hybrid Cloud for Storage**

      • AWS is pushing for ”hybrid cloud”
            • Part of your infrastructure is on-premises.
            • Part of your infrastructure is on the cloud.
      • This can be due to
            • Long cloud migrations
            • Security requirements
            • Compliance requirements
            • IT strategy
      • S3 is a proprietary storage technology (unlike EFS / NFS), so how do you expose the S3 data on-premise?
      • AWS Storage Gateway!
      
**AWS Storage Gateway**

      • Bridge between on-premise data and cloud data in S3.
      • Hybrid storage service to allow onpremises to seamlessly use the AWS Cloud.
      • Use cases: disaster recovery, backup & restore, tiered storage
      • Types of Storage Gateway:
            • File Gateway
            • Volume Gateway
            • Tape Gateway
            
**Amazon S3 – Summary**

      • Buckets vs Objects: global unique name, tied to a region.
      • S3 security: IAM policy, S3 Bucket Policy (public access), S3 Encryption.
      • S3 Websites: host a static website on Amazon S3.
      • S3 Versioning: multiple versions for files, prevent accidental deletes.
      • S3 Access Logs: log requests made within your S3 bucket.
      • S3 Replication: same-region or cross-region, must enable versioning.
      • S3 Storage Classes: Standard, IA, 1Z-IA, Intelligent, Glacier, Deep Archive.
      • S3 Lifecycle Rules: transition objects between classes.
      • Snowball / Snowmobile: import data onto S3 through a physical device.
      • Storage Gateway: hybrid solution to extend on-premises storage to S3.
