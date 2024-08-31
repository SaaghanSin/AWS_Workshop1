---
title : "Create Policy"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 2.1 </b> "
---

#### Create Policy

1. Go to [Identity and Access Management Control](https://us-east-1.console.aws.amazon.com/iam/home?region=ap-southeast-2#/home)
   - Click **Policies**.
   - Click **Create Policy**.

   ![Policy](/images/2.prerequisite/policy.png)

2. At the **Create Policy** page:
   - **Step 1: Specify permissions**
     - In the **Service** option box, choose **S3**.
     - In the **Actions allowed** field, choose **PutObject** from the **Write** criteria.
     - In the **Resource** option box, choose **All**.
     - Click **Next**.

     ![Policy](/images/2.prerequisite/createpolicy1.png)

   - **Step 2: Review and create**
     - In the **Policy name** field, write a meaningful name to identify this policy, such as **S3PutPolicy**.
     - Click **Create Policy**.

     ![Policy](/images/2.prerequisite/createpolicy2.png)

3. Similarly, create a policy for EventBridge Scheduler execution. Select Lambda as the service and set the access level to Limited: Write.

Now that you've created the necessary policies, you're ready to create an IAM role that will use these policies.