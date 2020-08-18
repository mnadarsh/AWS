# Deploying and Managing Infrastructure at Scale

  **What is CloudFormation**
  
    • CloudFormation is a declarative way of outlining your AWS.
      Infrastructure, for any resources (most of them are supported).
    • For example, within a CloudFormation template, you say:
        • I want a security group.
        • I want two EC2 instances using this security group.
        • I want an S3 bucket.
        • I want a load balancer (ELB) in front of these machines.
    • Then CloudFormation creates those for you, in the right order, with the
    exact configuration that you specify.
    
  **Benefits of AWS CloudFormation**
  
      • Infrastructure as code
          • No resources are manually created, which is excellent for control.
          • Changes to the infrastructure are reviewed through code.
          
      • Cost
          • Each resources within the stack is tagged with an identifier so you can easily see how
            much a stack costs you.
         • You can estimate the costs of your resources using the CloudFormation template.
          • Savings strategy: In Dev, you could automation deletion of templates at 5 PM and
            recreated at 8 AM, safely.
            
      • Productivity
          • Ability to destroy and re-create an infrastructure on the cloud on the .
          • Automated generation of Diagram for your templates!.
          • Declarative programming (no need to figure out ordering and orchestration).
          
      • Don’t re-invent the wheel
          • Leverage existing templates on the web!.
          • Leverage the documentation.
          
      • Supports (almost) all AWS resources:
          • Everything we’ll see in this course is supported.
          • You can use “custom resources” for resources that are not supported.
   
   ![stack_designer](https://github.com/mnadarsh/AWS/blob/master/Images/stack_designer.PNG "stack_designer")
   
  **Developer problems on AWS**
  
    • Managing infrastructure.
    • Deploying Code.
    • Configuring all the databases, load balancers, etc
    • Scaling concerns.
    
    • Most web apps have the same architecture (ALB + ASG).
    • All the developers want is for their code to run!.
    • Possibly, consistently across different applications and environments.
    
 **AWS Elastic Beanstalk Overview**
 
      • Elastic Beanstalk is a developer centric view of deploying an application on AWS.
      • It uses all the component’s we’ve seen before: EC2, ASG, ELB, RDS, etc…
      • But it’s all in one view that’s easy to make sense of!.
      • We still have full control over the configuration.
      
      • Beanstalk = Platform as a Service (PaaS).
      • Beanstalk is free but you pay for the underlying instances.
      
 **Elastic Beanstalk**
 
    • Managed service
        • Instance configuration / OS is handled by Beanstalk.
        • Deployment strategy is configurable but performed by Elastic Beanstalk.
        
    • Just the application code is the responsibility of the developer.
    
    • Three architecture models:
        • Single Instance deployment: good for dev.
        • LB + ASG: great for production or pre-production web applications.
        • ASG only: great for non-web apps in production (workers, etc..).
        
  ![Aws_code_deploy](https://github.com/mnadarsh/AWS/blob/master/Images/Aws_code_deploy.PNG "Aws_code_deploy")
  
 **AWS Systems Manager (SSM)**
 
      • Helps you manage your EC2 and On-Premises systems at scale.
      • Another Hybrid AWS service.
      • Get operational insights about the state of your infrastructure.
      • Suite of 10+ products.
      • Most important features are:
          • Patching automation for enhanced compliance.
          • Run commands across an entire fleet of servers.
          • Store parameter configuration with the SSM Parameter Store.
      • Works for both Windows and Linux OS.
      
![Aws_ssm](https://github.com/mnadarsh/AWS/blob/master/Images/Aws_ssm.PNG "Aws_ssm")

**AWS OpsWorks**

    • Chef & Puppet help you perform server configuration automatically, or repetitive actions.
    • They work great with EC2 & On-Premises VM.
    • AWS OpsWorks = Managed Chef & Puppet.
    • It’s an alternative to AWS SSM.
    • Only provision standard AWS resources:
      • EC2 Instances, Databases, Load Balancers, EBS volumes…
      
![Aws_opsworks](https://github.com/mnadarsh/AWS/blob/master/Images/Aws_opsworks.PNG "Aws_opsworks") 

**Deployment - Summary**

    • CloudFormation: (AWS only)
        • Infrastructure as Code, works with almost all of AWS resources.
        • Repeat across Regions & Accounts.
    • Beanstalk: (AWS only)
        • Platform as a Service (PaaS), limited to certain programming languages or Docker.
        • Deploy code consistently with a known architecture: ex, ALB + EC2 + RDS.
    • CodeDeploy (hybrid): deploy & upgrade any application onto servers.
    • Systems Manager (hybrid): patch, configure and run commands at scale.
    • OpsWorks (hybrid): managed Chef and Puppet in AWS.
