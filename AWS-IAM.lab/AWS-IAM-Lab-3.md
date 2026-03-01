## Activity - AWS Lambda Module 6 - Compute

## Lab overview

![IAM3](/images/Lab3.1.png)


In this hands-on activity, you will create an AWS Lambda function. You will also create an Amazon EventBridge event to trigger the function every minute. The function uses an AWS Identity and Access Management (IAM) role. This IAM role allows the function to stop an Amazon Elastic Compute Cloud (Amazon EC2) instance that is running in the Amazon Web Services (AWS) account.


## AWS service restrictions

In this lab environment, access to AWS services and service actions might be restricted to the ones that are needed to complete the lab instructions. You might encounter errors if you attempt to access other services or perform actions beyond the ones that are described in this lab.


## Accessing the AWS Management Console

1.	At the top of these instructions, choose **Start Lab**.
- The lab session starts.
- A timer displays at the top of the page and shows the time remaining in the session.

>[!NOTE]
>**Tip**: To refresh the session length at any time, choose **Start Lab** again before the timer reaches 0:00.

 - Before you continue, wait until the circle icon to the right of the AWS link in the upper-left corner turns green. 
 
2.	To connect to the **AWS** Management Console, choose the AWS link in the upper-left corner.
- A new browser tab opens and connects you to the console.

>[!NOTE]
>**Tip**: If a new browser tab does not open, a banner or icon is usually at the top of your browser with the message that your browser is preventing the site from opening pop-up windows. 
- Choose the banner or icon, and then choose **Allow pop-ups**.
 
3.	Arrange the AWS Management Console tab so that it displays along side these instructions. Ideally, you will be able to see both browser tabs at the same time, to make it easier to follow the lab steps.


## Getting Credit for your work

4. In the search box to the right of **Services**, search for and choose **Lambda** to open the AWS Lambda console.	

5. Choose **Create a function**.

6. In the **Create function** screen, configure these settings:
  - Choose **Author from scratch**
  -	Function name: _myStopinator_
  -	Runtime: **Python 3.11**
  -	Choose **Change default execution role**
  -	Execution role: **Use an existing role**
  -	Existing role: From the dropdown list, choose **myStopinatorRole**

7.	Choose **Create function**.


**Task 2: Configure the trigger**

In this task, you will configure a scheduled event to trigger the Lambda function by setting an Amazon EventBridge event as the event source (or trigger). 
The Lambda function can be configured to operate much like a cron job on a Linux server, or a scheduled task on a Microsoft Windows server. However, you do not need to have a server running to host it.

8.	Choose **Add trigger**.

9.	Choose the **Select a trigger** dropdown menu, and select **EventBridge (CloudWatch Events)**.

10.	For the rule, choose **Create a new rule** and configure these settings:

-	Rule name: _everyMinute_
-	Rule type: **Schedule expression**
-	Schedule expression: _rate(1 minute)_

>[!NOTE]
>A more realistic, schedule-based stopinator Lambda function would probably be triggered by using a cron expression instead of a rate expression. However, for the purposes of this activity, using a rate expression ensures that the Lambda function will be triggered soon enough that you can see the results_.

11.	Choose **Add**.


## Task 3: Configure the Lambda function

In this task, you will paste a few lines of code to update two values in the function code. You do not need to write code to complete this task.

12.	Below the **Function overview ** pane, choose **Code**, and then choose _lambda_function.py_ to display and edit the Lambda function code.

13.	In the **Code source** pane, delete the existing code. Copy the following code, and paste it in the box:

![IAM3](/images/Lab3.2.png)


>[!NOTE]
>After pasting the code into the Code source box, review line 5. If a period (.) was added, delete it.

14.	Replace the **<REPLACE_WITH_REGION>** placeholder with the actual Region that you are using. To do this:
Choose on the region on the top right corner and use the region code. For example, the region code for US East (N. Virginia) is _us-east-1_.

>[!NOTE]
>Important: Keep the single quotation marks (' ') around the Region in your code. For example, for the N. Virginia, it would be _'us-east-1'_


15.	**Challenge section**: Verify that an EC2 instance named instance1 is running in your account, and copy the instance1 **instance ID**.

You are encouraged to figure out how to do this task without specific step-by-step guidance. However, if you need detailed guidance, select this text to reveal detailed steps: Open another browser tab and go to https://console.aws.amazon.com/ec2. Choose Instances. Note that an EC2 instance named *instance1* exists, and that it is in a running state. From the Details tab of instance1, copy the instance ID (it will start with i-) 

Note: Leave this browser tab open. You will return to it in a moment. 

16.	Return to the **AWS Lambda console** browser tab, and replace **<REPLACE_WITH_INSTANCE_ID>** with the actual instance ID that you just copied.

> [!IMPORTANT]
> Keep the single quotation marks (' ') around the instance ID in your code.

Your code should now look similar to the following example. However, you might have a different value for the Region, and you will have a different value for the instance ID:

![IAM3](/images/Lab3.3.png)


17.	Choose the **File** menu and **Save** the changes. Then, in the **Code source** box, choose **Deploy**.

Your Lambda function is now fully configured. It should attempt to stop your instance every minute.

18.	Choose **Monitor** (the tab near the top of the page).

Note that one of the charts shows you how many times your function has been invoked. There is also a chart that shows the error count and the success rate as a percentage.

19.	Choose the **File** menu and **Save** the changes. Then, in the **Code source** box, choose **Deploy**.

Your Lambda function is now fully configured. It should attempt to stop your instance every minute.

20.	Choose **Monitor** (the tab near the top of the page).

>[!NOTE]
>That one of the charts shows you how many times your function has been invoked. There is also a chart that shows the error count and the success rate as a percentage.


## Activity complete

Congratulations! You have completed the activity.

----------- 



## Activity - AWS Elastic Beanstalk – Module 6

## Lab overview

This activity provides you with an Amazon Web Services (AWS) account where an AWS Elastic Beanstalk environment has been pre-created for you. You will deploy code to it and observe the AWS resources that make up the Elastic Beanstalk environment.


## AWS service restrictions

In this lab environment, access to AWS services and service actions might be restricted to the ones that are needed to complete the lab instructions. You might encounter errors if you attempt to access other services or perform actions beyond the ones that are described in this lab.


## Accessing the AWS Management Console

1.	At the top of these instructions, choose **Start Lab**.
-	The lab session starts.
-	A timer displays at the top of the page and shows the time remaining in the session.

>[!NOTE]
>Tip: To refresh the session length at any time, choose **Start Lab** again before the timer reaches 0:00.
o	Before you continue, wait until the circle icon to the right of the AWS link in the upper-left corner turns green.

2.	To connect to the AWS Management Console, choose the **AWS** link in the upper-left corner.
-	A new browser tab opens and connects you to the console.

>[!NOTE]
>Tip: If a new browser tab does not open, a banner or icon is usually at the top of your browser with the message that your browser is preventing the site from opening pop-up windows. Choose the banner or icon, and then choose **Allow pop-ups**.

3.	Arrange the AWS Management Console tab so that it displays along side these instructions. Ideally, you will be able to see both browser tabs at the same time, to make it easier to follow the lab steps.


## Getting Credit for your work

At the end of this lab you will be instructed to submit the lab to receive a score based on your progress.

>[!NOTE]
>Tip: The script that checks you works may only award points if you name resources and set configurations as specified. In particular, values in these instructions that appear in This Format should be entered exactly as documented (case-sensitive).


## Task 1: Access the Elastic Beanstalk environment

4.	In the console, in the search box to the right of to **Services**, search for and choose **Elastic Beanstalk**. 

A page titled **Environments** should open, and it should show a table that lists the details for an existing Elastic Beanstalk application. 

>[!NOTE]
>If the status in the Health column is not Ok, it has not finished starting yet. Wait a few moments, and it should change to Ok.

![IAM3](/images/Lab3.4.png)

5.	Under the **Environment name** column, choose the name of the environment.

The **Dashboard** page for your Elastic Beanstalk environment opens.

6.	Notice that the page shows that the health of your application is Ok.
   
The Elastic Beanstalk environment is ready to host an application. However, it does not yet have running code.

7.	Test access to the environment.

-	Near the top of the page, choose the Domain link (the URL ends in elasticbeanstalk.com).
When you choose the URL, a new browser tab opens. However, you should see that it displays an **HTTP Status 404 - Not Found** message. 

This behavior is expected because this application server doesn't have an application running on it yet. 

-	Return to the Elastic Beanstalk console.
In the next step, you will deploy code in your Elastic Beanstalk environment.


## Task 2: Deploy a sample application to Elastic Beanstalk

8.	To download a sample application, choose this link: https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/samples/tomcat.zip

9. Back in the Elastic Beanstalk Dashboard, choose **Upload and Deploy**.

10. Choose **File**, then navigate to and open the **tomcat.zip** file that you just downloaded.

11.	Choose Deploy.

It will take a minute or two for Elastic Beanstalk to update your environment and deploy the application.

12.	After the deployment is complete, choose the Domain URL link (or, if you still have the browser tab that displayed the 404 status, refresh that page).

The web application that you deployed displays.

![IAM3](/images/Lab3.5.png)

Congratulations, you have successfully deployed an application on Elastic Beanstalk!

13.	Back in the Elastic Beanstalk console, choose **Configuration** in the left pane.
Notice the details here.

_For example, in the **Instance traffic and scaling** panel, it indicates the EC2 Security groups, minimum and maximum instances, and instance type details of the Amazon Elastic Compute Cloud (Amazon EC2) instances that are hosting your web application._

14.	In the **Networking, database, and tags** panel, no configuration details display, because the environment does not include a database.

15.	In the **Networking**, **database**, and **tags** row, choose **Edit**

>[!NOTE]
>That you could easily enable a database to this environment if you wanted to: you only need to set a few basic configurations and choose Apply. (However, for the purposes of this activity, you do not need to add a database.)

- Choose **Cancel** at the bottom of the screen.

16.	In the left panel under Environment, choose **Monitoring**.

Browse through the charts to see the kinds of information that are available to you.


## Task 3: Explore the AWS resources that support your application

17.	In the console, in the search box to the right of to **Services**, search for and choose **EC2**

18.	Choose **Instances**.

>[!NOTE]
>That two instances that support your web application are running (they both contain samp in their names). 


19.	If you want to continue exploring the Amazon EC2 service resources that were created by Elastic Beanstalk, feel free to explore them. You will find:
-	A security group with **port 80** open
-	A load balancer that both instances belong to
-	An _Auto Scaling group_ that runs from two to six instances, depending on the network load

Though Elastic Beanstalk created these resources for you, you still have access to them.

## Activity complete

Congratulations! You have completed the activity.



























