# EC2 Instance Storage

**What’s an EBS Volume?**

    • An EBS (Elastic Block Store) Volume is a network drive you can attach to your instances while they run.
    • It allows your instances to persist data, even after their termination.
    • They can only be mounted to one instance at a time (at the CCP level).
    • They are bound to a specific availability zone.
    • Analogy: Think of them as a “network USB stick”.
    • Free tier: 30 GB of free EBS storage of type gp2 per month.
    
**EBS Volume**

    • It’s a network drive (i.e. not a physical drive).
    • It uses the network to communicate the instance, which means there might be a bit of latency.
    • It can be detached from an EC2 instance and attached to another one quickly
    • It’s locked to an Availability Zone (AZ)
    • An EBS Volume in us-east-1a cannot be attached to us-east-1b.
    • To move a volume across, you first need to snapshot it.
    • Have a provisioned capacity (size in GBs, and IOPS).
    • You get billed for all the provisioned capacity.
    • You can increase the capacity of the drive over time.
    
**EBS Snapshots**

    • Make a backup (snapshot) of your EBS volume at a point in time.
    • Not necessary to detach volume to do snapshot, but recommended.
    • Can copy snapshots across AZ or Region.
    
**AMI Overview**

    • AMI = Amazon Machine Image.
    • AMI are a customization of an EC2 instance.
      • You add your own software, configuration, operating system, monitoring…
      • Faster boot / configuration time because all your software is pre-packaged.
    • AMI are built for a specific region (and can be copied across regions).
    • You can launch EC2 instances from:
      • A Public AMI: AWS provided.
      • Your own AMI: you make and maintain them yourself.
      • An AWS Marketplace AMI: an AMI someone else made (and potentially sells).
      
**AMI Process (from an EC2 instance)**

    • Start an EC2 instance and customize it.
    • Stop the instance (for data integrity).
    • Build an AMI – this will also create EBS snapshots.
    • Launch instances from other AMIs.
    
**EC2 Instance Store**

    • EBS volumes are network drives with good but “limited” performance.
    • If you need a high-performance hardware disk, use EC2 Instance Store.
    • Better I/O performance
    • EC2 Instance Store lose their storage if they’re stopped (ephemeral).
    • Good for buffer / cache / scratch data / temporary content.
    • Risk of data loss if hardware fails.
    • Backups and Replication are your responsibility.
    
**EFS – Elastic File System**

    • Managed NFS (network file system) that can be mounted on 100s of EC2.
    • EFS works with Linux EC2 instances in multi-AZ.
    • Highly available, scalable, expensive (3x gp2), pay per use, no capacity planning.
    
**Shared Responsibility Model for EC2 Storage**

  *AWS*
    
      • Infrastructure.
      • Replication for data for EBS volumes & EFS drives.
      • Replacing faulty hardware.
      • Ensuring their employees cannot access your data.
      
  *User*
  
      • Setting up backup / snapshot procedures.
      • Setting up data encryption.
      • Responsibility of any data on the drives.
      • Understanding the risk of using EC2 Instance Store.
      
**EC2 Instance Storage - Summary**
  
      • EBS volumes:
        • network drives attached to one EC2 instance at a time.
        • Mapped to an Availability Zones.
        • Can use EBS Snapshots for backups / transferring EBS volumes across AZ.
      • AMI: create ready-to-use EC2 instances with our customizations.
      • EC2 Instance Store:
        • High performance hardware disk attached to our EC2 instance.
        • Lost if our instance is stopped / terminated.
      • EFS: network file system, can be attached to 100s of instances in a region.
