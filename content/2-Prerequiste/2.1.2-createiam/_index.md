---
title : "Create IAM role"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 2.2</b> "
---

#### Create IAM Role

1. Go to [Identity and Access Management Control](https://us-east-1.console.aws.amazon.com/iam/home?region=ap-southeast-2#/home)
   - Click **Roles**.
   - Click **Create role**.

   ![IAM](/images/2.prerequisite/IAM.png)

2. At the **Create role** page:
   - **Step 1: Select trusted identity**
     - In the **Trusted entity type** option box, choose **AWS service**.
     - In the **Use case** field, choose **Lambda**.
     - Click **Next**.

     ![IAM](/images/2.prerequisite/createiam1.png)

   - **Step 2: Add permissions**
     - In the **Permissions policies** field, choose the policy you have create before with **AWSLambdaBasicExecutionRole**. In the guide, it's **s3PutPolicy**.
     - Click **Next**.

     ![Policy](/images/2.prerequisite/createiam2.png)

   - **Step 3: Name, review, and create**
     - In the **Role name** field, write a meaningful name to identify this policy, such as **s3PutObjectRole**.
     - Click **Create role**.

     ![Policy](/images/2.prerequisite/createiam3.png)
3. Similarly, creating an IAM Role for EventBridge Scheduler:

  - Repeat the above steps to create another IAM role, but this time, in Step 2: Add permissions, select the EventBridge Scheduler policy you created (e.g., EventBridgeSchedulerExecutionPolicy) along with AWSLambdaBasicExecutionRole.
  - Name this role something like EventBridgeSchedulerRole.
  - Click Create role.
  
After this, move on to download the needed library for layer of the lambda function. In this workshop it is **Request** library.