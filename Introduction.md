# Cloud Computing

1. Cloud computing is the on-demand delivery of compute power, database storage,
applications, and other IT resources.
2. Through a cloud services platform with pay-as-you-go pricing.
3. You can provision exactly the right type and size of computing resources you need.
4. You can access as many resources as you need, almost instantly.
5. Simple way to access servers, storage, databases and a set of application services.
6. Amazon Web Services owns and maintains the network-connected hardware required for these application services, while you provision and use what you need via a web application.

## The Deployment Models of the Cloud

  1. Private Cloud:
  
    . Cloud services used by a single organization, not exposed to the public.
    . Complete control and Security for sensitive applications.
    . Meet specific business needs.
    
  2. Public Cloud
  
    . Cloud resources owned and operated by a thirdparty cloud service provider delivered over the Internet.
    
  3. Hybrid Cloud
  
    . Keep some servers on premises and extend some capabilities to the Cloud.
    . Control over sensitive assets in your private infrastructure.
    . Flexibility and costeffectiveness of the public cloud
    
 ## The Five Characteristics of Cloud Computing
 
    1. On-demand self service:
          • Users can provision resources and use them without human interaction from the service provider.
          
    2. Broad network access:
         • Resources available over the network, and can be accessed by diverse client platforms.
         
    3. Multi-tenancy and resource pooling:
        • Multiple customers can share the same infrastructure and applications with security and privacy.
        • Multiple customers are serviced from the same physical resources.
        
    4. Rapid elasticity and scalability:
        • Automatically and quickly acquire and dispose resources when needed.
        • Quickly and easily scale based on demand.
        
    5. Measured service:
        • Usage is measured, users pay correctly for what they have used.
        
  ## Types of Cloud Computing
    
    1.  Infrastructure as a Service (IaaS)
        • Provide building blocks for cloud IT.
        • Provides networking, computers, data storage space.
        • Highest level of flexibility.
        • Easy parallel with traditional on-premises IT.
        
    2.  Platform as a Service (PaaS)
        • Removes the need for your organization to manage the underlying infrastructure.
        • Focus on the deployment and management of your applications.
        
    3.  Software as a Service (SaaS)
        • Completed product that is run and managed by the service provider.
        
   ## Pricing of the Cloud – Quick Overview
   
   *AWS has 3 pricing fundamentals, following the pay-as-you-go pricing model.*
    
      1 Compute: 
          • Pay for compute time.
          
      2 Storage:
          • Pay for data stored in the Cloud.
          
      3 Data transfer OUT of the Cloud:
          • Data transfer IN is free
          
  ## AWS Global Infrastructure
  
    • AWS Regions.
    • AWS Availability Zones.
    • AWS Data Centers.
    • AWS Edge Locations / Points of Presence.
    
   **AWS Regions**
        
    • AWS has Regions all around the world.
    • Names can be us-east-1, eu-west-3….
    • A region is a cluster of data centers.
    • Most AWS services are region-scoped.
    
   **AWS Availability Zones**
   
    • Each region has many availability zones
        (usually 3, min is 2, max is 6). Example:
        • ap-southeast-2a
        • ap-southeast-2b
        • ap-southeast-2c
    • Each availability zone (AZ) is one or more discrete data centers with redundant power, networking, and connectivity.
    • They’re separate from each other, so that they’re isolated from disasters.
    • They’re connected with high bandwidth, ultra-low latency networking.
    
  **AWS Points of Presence (Edge Locations)**
  
   • Amazon has 216 Points of Presence (205 Edge Locations & 11 Regional Caches) in 84 cities across 42 countries.
   • Content is delivered to end users with lower latency.
    
  ## Tour of the AWS Console
  
   **AWS has Global Services:**
 
    • Identity and Access Management (IAM).
    • Route 53 (DNS service).
    • CloudFront (Content Delivery Network).
    • WAF (Web Application Firewall).
    
  **Most AWS services are Region-scoped:**
  
    • Amazon EC2 (Infrastructure as a Service).
    • Elastic Beanstalk (Platform as a Service).
    • Lambda (Function as a Service).
    • Rekognition (Software as a Service).
    
**Region Table:**  https://aws.amazon.com/about-aws/global-infrastructure/regional-product-services


