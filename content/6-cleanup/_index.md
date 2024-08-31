+++
title = "Clean up resources"
date = 2022
weight = 6
chapter = false
pre = "<b>6. </b>"
+++

We will take the following steps to delete the resources we created in this exercise.

#### Delete Event schedule
1. Go to [Amazon EventBridge](https://ap-southeast-2.console.aws.amazon.com/events/home?region=ap-southeast-2#/rules?redirect_from_cwe=true)
   + If you have not disable the schedule then click into the schedule you have create for this workshop.
   + Click **Disable**, an message box will appear then choose **Disable**
2. After disable the schedule, click **Delete**. An message box will appear then choose **Disable**

![Clean](/images/6.clean/cleand1.png)
![Clean](/images/6.clean/cleand2.png)
#### Delete Lambda function
1. Go to [Lambda Console](https://ap-southeast-2.console.aws.amazon.com/lambda/home?region=ap-southeast-2#/functions)
   + Click on the function we created for this workshop.
   + Click **Action** option box then choose **Delete**.
   + Input **delete**, then click **Delete** to proceed to delete the function


![Clean](/images/6.clean/cleanf.png)
#### Delete S3 bucket

1. Go to [S3 service management console](https://s3.console.aws.amazon.com/s3/home)
   + Click on the S3 bucket we created for this workshop.
   + Click **Empty**.
   + Enter **permanently delete**, then click **Empty** to proceed to delete the object in the bucket.
   + Click **Exit**.

2. After deleting all objects in the bucket, click **Delete**
3. Enter the name of the S3 bucket, then click **Delete bucket** to proceed with deleting the S3 bucket.

![Clean](/images/6.clean/003-clean.png)

