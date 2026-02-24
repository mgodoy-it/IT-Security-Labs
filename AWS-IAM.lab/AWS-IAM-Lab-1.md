## Lab 1: Introduction to AWS IAM

AWS Identity and Access Management (IAM) is a web service that enables Amazon Web Services (AWS) customers to manage users and user permissions in AWS. With IAM, you can centrally manage users, security credentials such as access keys, and permissions that control which AWS resources users can access.

## Lab overview and objectives

This lab will demonstrate:

![IAM1](/images/Lab1.1.png)


- Exploring pre-created IAM Users and Groups

- Inspecting IAM policies as applied to the pre-created groups

- Following a real-world scenario, adding users to groups with specific capabilities enabled

- Locating and using the IAM sign-in URL

- Experimenting with the effects of policies on service access


## AWS service restrictions

In this lab environment, access to AWS services and service actions might be restricted to the ones that are needed to complete the lab instructions. You might encounter errors if you attempt to access other services or perform actions beyond the ones that are described in this lab.

 

## AWS Identity and Access Management

AWS Identity and Access Management (IAM) can be used to:

- Manage IAM Users and their access: You can create Users and assign them individual security credentials (access keys, passwords, and multi-factor authentication devices). You can manage permissions to control which operations a User can perform.

- Manage IAM Roles and their permissions: An IAM Role is similar to a User, in that it is an AWS identity with permission policies that determine what the identity can and cannot do in AWS. However, instead of being uniquely associated with one person, a Role is intended to be assumable by anyone who needs it.

- Manage federated users and their permissions: You can enable identity federation to allow existing users in your enterprise to access the AWS Management Console, to call AWS APIs and to access resources, without the need to create an IAM User for each identity.


## Accessing the AWS Management Console

1. At the top of these instructions, choose  **Start Lab**.

The lab session starts.

A timer displays at the top of the page and shows the time remaining in the session.

**Tip: To refresh the session length at any time, choose  Start Lab again before the timer reaches 0:00.**

Before you continue, wait until the circle icon to the right of the AWS  link in the upper-left corner turns green. 

 

2. To connect to the AWS Management Console, choose the AWS link in the upper-left corner.

A new browser tab opens and connects you to the console.

**Tip: If a new browser tab does not open, a banner or icon is usually at the top of your browser with the message that your browser is preventing the site from opening pop-up windows. Choose the banner or icon, and then choose Allow pop-ups.**

3. Arrange the AWS Management Console tab so that it displays along side these instructions. Ideally, you will be able to see both browser tabs at the same time, to make it easier to follow the lab steps.


## Getting Credit for your work

At the end of this lab you will be instructed to submit the lab to receive a score based on your progress.

** Tip: The script that checks you works may only award points if you name resources and set configurations as specified. In particular, values in these instructions that appear in This Format should be entered exactly as documented (case-sensitive).
**


## Task 1: Explore the Users and Groups

4. In this task, you will explore the Users and Groups that have already been created for you in IAM.

In the search box to the right of **Services**, search for and choose IAM to open the **IAM** console.

5. In the navigation pane on the left, choose Users.

The following **IAM** Users have been created for you:

- user-1

- user-2

- user-3


6. Choose the **user-1 **link.

This will bring to a summary page for user-1. The Permissions tab will be displayed.

7. Notice that **user-1** does not have any permissions.

8. Choose the **Groups** tab.

**user-1** also is not a member of any groups.


Choose the **Security credentials** tab.

user-1 is assigned a **Console password**.


10. In the navigation pane on the left, choose **User groups**.

   The following groups have already been created for you:

- EC2-Admin

- EC2-Support

- S3-Support

  

11. Choose the **EC2-Support** group link.

This will bring you to the summary page for the **EC2-Support** group.


12. Choose the **Permissions** tab.

This group has a Managed Policy associated with it, called **AmazonEC2ReadOnlyAccess**. Managed Policies are pre-built policies (built either by AWS or by your administrators) that can be attached to IAM Users and Groups. When the policy is updated, the changes to the policy are immediately apply against all Users and Groups that are attached to the policy.

 

13. Choose the plus (+) icon next to the AmazonEC2ReadOnlyAccess policy to view the policy details.

**Note**: A policy defines what actions are allowed or denied for specific AWS resources. 

This policy is granting permission to List and Describe information about EC2, Elastic Load Balancing, CloudWatch and Auto Scaling. This ability to view resources, but not modify them, is ideal for assigning to a Support role.

The basic structure of the statements in an IAM Policy is:

- **Effect** says whether to Allow or Deny the permissions.

- **Action** specifies the API calls that can be made against an AWS Service (eg cloudwatch:ListMetrics).

- **Resource** defines the scope of entities covered by the policy rule (eg a specific Amazon S3 bucket or Amazon EC2 instance, or * which means any resource).

 
14. Choose the minus icon (-) to hide the policy details.

15. In the navigation pane on the left, choose **User groups**.

16. Choose the **S3-Support** group link and then choose the **Permissions** tab.

 The S3-Support group has the **AmazonS3ReadOnlyAccess** policy attached.

 

17. Choose the plus (+) icon to view the policy details.

This policy grants permissions to Get and List resources in Amazon S3.

18. Choose the minus icon (-) to hide the policy details.


19. In the navigation pane on the left, choose User groups.

20 Choose the **EC2-Admin** group link and then choose the **Permissions** tab. 

This Group is slightly different from the other two. Instead of a Managed Policy, it has an Inline Policy, which is a policy assigned to just one User or Group. Inline Policies are typically used to apply permissions for one-off situations.

 
21. Choose the plus (+) icon to view the policy details.

This policy grants permission to view (Describe) information about Amazon EC2 and also the ability to Start and Stop instances.

22. Choose the minus icon (-) to hide the policy details.


## Business Scenario

For the remainder of this lab, you will work with these Users and Groups to enable permissions supporting the following business scenario:

Your company is growing its use of Amazon Web Services, and is using many Amazon EC2 instances and a great deal of Amazon S3 storage. You wish to give access to new staff depending upon their job function:


















