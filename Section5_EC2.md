# Amazon EC2

      • EC2 is one of the most popular of AWS offering.
      • EC2 = Elastic Compute Cloud = Infrastructure as a Service.
      • It mainly consists in the capability of :
                  • Renting virtual machines (EC2).
                  • Storing data on virtual drives (EBS).
                  • Distributing load across machines (ELB).
                  • Scaling the services using an auto-scaling group (ASG).
      • Knowing EC2 is fundamental to understand how the Cloud works.


**EC2 sizing & configuration options**

      • Operating System (OS): Linux or Windows.
      • How much compute power & cores (CPU).
      • How much random-access memory (RAM).
      • How much storage space:
             • Network-attached (EBS & EFS).
             • hardware (EC2 Instance Store).
             • Network card: speed of the card, Public IP address.
             • Firewall rules: security group.
             • Bootstrap script (configure at first launch): EC2 User Data.
      
      • Note: t2.micro is part of the AWS free tier (up to 750 hours per month).

**Introduction to Security Groups**

       • Security Groups are the fundamental of network security in AWS.
       • They control how traffic is allowed into or out of our EC2 Instances.
       • Security groups only contain allow rules.
       • Security groups rules can reference by IP or by security group.

**Security Groups Deeper Dive**

      • Security groups are acting as a “firewall” on EC2 instances
      • They regulate:
             • Access to Ports.
             • Authorised IP ranges – IPv4 and IPv6.
             • Control of inbound network (from other to the instance).
             • Control of outbound network (from the instance to other).
      
**Classic Ports to know**
 
      • 22 = SSH (Secure Shell) - log into a Linux instance
      • 21 = FTP (File Transport Protocol) – upload files into a file share
      • 22 = SFTP (Secure File Transport Protocol) – upload files using SSH
      • 80 = HTTP – access unsecured websites
      • 443 = HTTPS – access secured websites
      • 3389 = RDP (Remote Desktop Protocol) – log into a Windows instance.
      
**EC2 Instances Purchasing Options**

      • On-Demand Instances: short workload, predictable pricing
      • Reserved: (MINIMUM 1 year)
            • Reserved Instances: long workloads
            • Convertible Reserved Instances: long workloads with flexible instances
            • Scheduled Reserved Instances: example – every Thursday between 3 and 6 pm
      • Spot Instances: short workloads, cheap, can lose instances (less reliable)
      • Dedicated Hosts: book an entire physical server, control instance placement
      • Dedicated Instances: no other customers will share your hardware.
      
      
 **EC2 On Demand**
 
            • Pay for what you use:
            • Linux - billing per second, after the first minute.
            • All other operating systems (ex: Windows) - billing per hour.
            • Has the highest cost but no upfront payment.
            • No long-term commitment.
            • Recommended for short-term and un-interrupted workloads, where you can't predict how the application will behave.
            
 **EC2 Reserved Instances**
   
            • Up to 72% discount compared to On-demand.
            • Reservation period: 1 year = + discount | 3 years = +++ discount.
            • Purchasing options: no upfront | partial upfront = + | All upfront = ++ discount.
            • Reserve a specific instance type.
            • Recommended for steady-state usage applications (think database).
            • Convertible Reserved Instance
                  • can change the EC2 instance type.
                  • Up to 45% discount.
            • Scheduled Reserved Instances
                  • launch within time window you reserve.
                  • When you require a fraction of day / week / month.
                  • Commitment for 1 year only.
                  
**EC2 Spot Instances**

            • Can get a discount of up to 90% compared to On-demand
            • Instances that you can “lose” at any point of time if your max price is less than the current spot price
            • The MOST cost-efficient instances in AWS.
            
     • Useful for workloads that are resilient to failure
            • Batch jobs
            • Data analysis
            • Image processing
            • Any distributed workloads
            • Workloads with a flexible start and end time
      • Not suitable for critical jobs or databases
      
**EC2 Dedicated Hosts**
 
      • An Amazon EC2 Dedicated Host is a physical server with EC2 instance capacity fully dedicated to your use. Dedicated Hosts can help you.
        address compliance requirements and reduce costs by allowing you to use your existing server-bound software licenses.
      • Allocated for your account for a 3-year period reservation.
      • More expensive.
      • Useful for software that have complicated licensing model (BYOL – Bring Your Own License).
      • Or for companies that have strong regulatory or compliance needs.
      
**EC2 Dedicated Instances**
 
      • Instances running on hardware that’s dedicated to you.
      • May share hardware with other instances in same account.
      • No control over instance placement (can move hardware after Stop / Start).
      
      
**Which purchasing option is right for me?**

      • On demand: coming and staying in resort whenever we like, we pay the full price.
      • Reserved: like planning ahead and if we plan to stay for a long time, we may get a good discount.
      • Spot instances: the hotel allows people to bid for the empty rooms and the highest bidder keeps the rooms. You can get kicked out at any time.
      • Dedicated Hosts: We book an entire building of the resort
      
**Shared Responsibility Model for EC2**

   *AWS*
   
            • Infrastructure (global network security).
            • Isolation on physical hosts.
            • Replacing faulty hardware.
            • Compliance validation.
            
   *User*
   
           • Security Groups rules.
           • Operating-system patches and updates.
           • Software and utilities installed on the EC2 instance.
           • IAM Roles assigned to EC2 & IAM user access management.
           • Data security on your instance.
    
**EC2 Section – Summary**

      • EC2 Instance: AMI (OS) + Instance Size (CPU + RAM) + Storage + security groups + EC2 User Data.
      • Security Groups: Firewall attached to the EC2 instance.
      • EC2 User Data: Script launched at the first start of an instance.
      • SSH: start a terminal into our EC2 Instances (port 22).
      • EC2 Instance Role: link to IAM roles.
      • Purchasing Options: On-Demand, Spot, Reserved (Standard + Convertible + Scheduled), Dedicated Host, Dedicated Instance.
