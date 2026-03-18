## Lab 4: Working with EBS

## Lab Overview

![IAM4](/images/Lab4.1.png)


## This lab focuses on Amazon Elastic Block Store (Amazon EBS), a key underlying storage mechanism for Amazon EC2 instances. In this lab, you will learn how to create an Amazon EBS volume, attach it to an instance, apply a file system to the volume, and then take a snapshot backup.

## Topics covered

By the end of this lab, you will be able to:
-	Create an Amazon EBS volume
-	Attach and mount your volume to an EC2 instance
-	Create a snapshot of your volume
-	Create a new volume from your snapshot
-	Attach and mount the new volume to your EC2 instance


## AWS service restrictions

In this lab environment, access to AWS services and service actions might be restricted to the ones that are needed to complete the lab instructions. You might encounter errors if you attempt to access other services or perform actions beyond the ones that are described in this lab.


## What is Amazon Elastic Block Store?

Amazon Elastic Block Store (Amazon EBS) offers persistent storage for Amazon EC2 instances. Amazon EBS volumes are network-attached and persist independently from the life of an instance. Amazon EBS volumes are highly available, highly reliable volumes that can be leveraged as an Amazon EC2 instances boot partition or attached to a running Amazon EC2 instance as a standard block device.

When used as a boot partition, Amazon EC2 instances can be stopped and subsequently restarted, enabling you to pay only for the storage resources used while maintaining your instance's state. Amazon EBS volumes offer greatly improved durability over local Amazon EC2 instance stores because Amazon EBS volumes are automatically replicated on the backend (in a single Availability Zone).

For those wanting even more durability, Amazon EBS provides the ability to create point-in-time consistent snapshots of your volumes that are then stored in Amazon Simple Storage Service (Amazon S3) and automatically replicated across multiple Availability Zones. These snapshots can be used as the starting point for new Amazon EBS volumes and can protect your data for long-term durability. You can also easily share these snapshots with co-workers and other AWS developers.

This lab guide explains basic concepts of Amazon EBS in a step-by-step fashion. However, it can only give a brief overview of Amazon EBS concepts. For further information, see the [Amazon EBS documentation. ](http://aws.amazon.com/ebs/)

## Amazon EBS Volume Features

**Amazon EBS volumes deliver the following features:**

-	Persistent storage: Volume lifetime is independent of any particular Amazon EC2 instance.
-	General purpose: Amazon EBS volumes are raw, unformatted block devices that can be used from any operating system.
-	High performance: Amazon EBS volumes are equal to or better than local Amazon EC2 drives.
-	High reliability: Amazon EBS volumes have built-in redundancy within an Availability Zone.
-	Designed for resiliency: The AFR (Annual Failure Rate) of Amazon EBS is between 0.1% and 1%.
-	Variable size: Volume sizes range from 1 GB to 16 TB.
-	Easy to use: Amazon EBS volumes can be easily created, attached, backed up, restored, and deleted.


## Accessing the AWS Management Console

1.	At the top of these instructions, choose **Start Lab**.
  o	The lab session starts.
  o	A timer displays at the top of the page and shows the time remaining in the session.
  Tip: To refresh the session length at any time, choose **Start Lab** again before the timer reaches 0:00.
  o	Before you continue, wait until the circle icon to the right of the AWS link in the upper-left corner turns green. 
 
2.	To connect to the AWS Management Console, choose the **AWS** link in the upper-left corner.
  o	A new browser tab opens and connects you to the console.
 _ Tip: If a new browser tab does not open, a banner or icon is usually at the top of your browser with the message that your browser is preventing the site from opening pop-up windows. Choose the banner or icon, and then choose Allow pop-ups._



