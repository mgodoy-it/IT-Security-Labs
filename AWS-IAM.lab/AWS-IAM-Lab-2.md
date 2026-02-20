<!--

Lab 1 - Intro to AWS IAM

AWS IAM is a web service that allows AWS customers to securely manage users and their permissions within AWS. With IAM, you can centrally manage users, security credentials (such as access keys), and define permissions that control which AWS resources users are allowed to access.

-->

## Lab - 2 Build your VPC and Launch a Web Server

## Lab overview and objectives

In this lab, you will use Amazon Virtual Private Cloud (VPC) to create your own VPC and add additional components to produce a customized network. 
You will also create a security group. You will then configure and customize an EC2 instance to run a web server and you will launch the EC2 instance to run in a subnet in the VPC.

**Amazon Virtual Private Cloud (Amazon VPC)** enables you to launch Amazon Web Services (AWS) resources into a virtual network that you defined. This virtual network closely resembles a traditional network that you would operate in your own data center, with the benefits of using the scalable infrastructure of AWS. You can create a VPC that spans multiple Availability Zones.

After completing this lab, you should be able to do the following:

- Create a VPC.
- Create subnets.
- Configure a security group.
- Launch an EC2 instance into a VPC. 

## AWS service restrictions

In this lab environment, access to AWS services and service actions might be restricted to the ones that are needed to complete the lab instructions. You might encounter errors if you attempt to access other services or perform actions beyond the ones that are described in this lab.
 
Scenario

In this lab you build the following infrastructure:

![IAM2](/images/Lab2.1.png)


## Accessing the AWS Management Console

1.	At the top of these instructions, choose **Start Lab**.
   
 - The lab session starts.
 - A timer displays at the top of the page and shows the time remaining in the session.

**Tip: To refresh the session length at any time, choose Start Lab again before the timer reaches 0:00.**

 - Before you continue, wait until the circle icon to the right of the AWS link in the upper-left corner turns green. 


2.	To connect to the AWS Management Console, choose the AWS link in the upper-left corner.

- A new browser tab opens and connects you to the console.
  
**Tip: If a new browser tab does not open, a banner or icon is usually at the top of your browser with the message that your browser is preventing the site from opening pop-up windows. Choose the banner or icon, and then choose Allow pop-ups.**

3.	Arrange the AWS Management Console tab so that it displays along side these instructions. Ideally, you will be able to see both browser tabs at the same time, to make it easier to follow the lab steps.


At the end of this lab you will be instructed to submit the lab to receive a score based on your progress.

**Tip: The script that checks you works may only award points if you name resources and set configurations as specified. In particular, values in these instructions that appear in This Format should be entered exactly as documented (case-sensitive).
**

## Task 1: Create Your VPC

In this task, you will use the VPC and more option in the VPC console to create multiple resources, including a VPC, an Internet Gateway, a public subnet and a private subnet in a single Availability Zone, two route tables, and a NAT Gateway.
 
4.	In the search box to the right of **Services**, search for and choose **VPC** to open the VPC console.

5.	Begin creating a VPC.
   
-	In the top right of the screen, verify that **N. Virginia (us-east-1)** is the region. 
-	Choose the **VPC dashboard** link which is towards the top left of the console.
-	Next, choose Create VPC.
  
**Note: If you do not see a button with that name, choose the Launch VPC Wizard button instead.
**

6.	Configure the VPC details in the VPC settings panel on the left:
   
-	Choose **VPC and more**.
-	Under **Name tag auto-generation**, keep Auto-generate selected, however change the value from project to lab.
-	Keep the **IPv4 CIDR block** set to 10.0.0.0/16
-	For **Number of Availability Zones**, choose 1.
-	For **Number of public subnets**, keep the 1 setting.
-	For **Number of private subnets**, keep the 1 setting.
-	Expand the **Customize subnets CIDR blocks** section
-	Change **Public subnet CIDR block in us-east-1a** to 10.0.0.0/24
-	Change **Private subnet CIDR block in us-east-1a** to 10.0.1.0/24
-	Set **NAT** gateways to **In 1 AZ**.
-	Set **VPC endpoints** to None.
-	Keep both **DNS hostnames** and **DNS resolution** <u> enabled </u>.


7.	In the Preview panel on the right, confirm the settings you have configured.
   
- VPC: lab-vpc
- Subnets:
   -	us-east-1a
   - Public subnet name: lab-subnet-public1-us-east-1a
   -	Private subnet name: lab-subnet-private1-us-east-1a

-	Route tables
  - lab-rtb-public
  - lab-rtb-private1-us-east-1a

-	Network connections
  -	lab-igw
  -	lab-nat-public1-us-east-1a 

8.	At the bottom of the screen, choose Create VPC

The VPC resources are created. The NAT Gateway will take a few minutes to activate. 

Please wait until all the resources are created before proceding to the next step.


9.	Once it is complete, choose View VPC
    
The wizard has provisioned a VPC with a public subnet and a private subnet in one Availability Zone with route tables for each subnet. It also created an Internet Gateway and a NAT Gateway. 

To view the settings of these resources, browse through the VPC console links that display the resource details. 

For example, choose **Subnets** to view the subnet details and choose Route tables to view the route table details. 

The diagram below summarizes the VPC resources you have just created and how they are configured.


