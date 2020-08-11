# Amazon EC2

• EC2 is one of the most popular of AWS’ offering.
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
      
      
