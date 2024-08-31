---
title : "Auto pipeline"
date :  "`r Sys.Date()`" 
weight : 5 
chapter : false
pre : " <b> 5. </b> "
---

#### Create schedule event


1. Go to [Amazon EventBridge](https://ap-southeast-2.console.aws.amazon.com/events/home?region=ap-southeast-2#/rules?redirect_from_cwe=true)
   - Click **Schedules**.
   - Click **Create schedule**.

   ![Pipeline](/images/5.pipeline/event.png)

2. At the **Create schedule** page:
   - **Step 1: Specify schedule detail**
     - In the **Schedule name** field, write a meaningful name to identify this policy, such as **uploadToS3**.
     - In the **Schedule pattern section**, set the timing for the event. For this workshop, you'll configure it to fetch data from an API every 5 minutes:
        - In the **Occurrence** option box, choose **Recurring schedule**.
        - Depending on your familiarity with scheduling:
            - If you're familiar with Cron expressions, you can enter your expression in the Cron-based schedule field. You can refer to [this guide](https://docs.oracle.com/cd/E12058_01/doc/doc.1014/e12030/cron_expressions.htm) for help.
            - If you prefer a simpler approach, select Rate-based schedule, enter 5 in the value field, and choose minutes from the dropdown.
     - In the **Flexible time window** option box, choose **5 minutes**.
     - Click **Next**.

   ![Pipeline](/images/5.pipeline/eventp.png)

   - **Step 2: Select target**
     - In the **Target detail** section, choose **Templated targets** then choose **Invoke** from AWS Lambda API.
     - In the **Invoke** section, choose the function you have create before in part 4.1.
     - Click **Next**.
    ![Pipeline](/images/5.pipeline/eventapi.png)    
   - **Step 3: Setting**
     - In the **Permissions** section, choose **Use existing role** then choose the IAM role you have create before in part 2.2
     - Click **Next**.
   ![Pipeline](/images/5.pipeline/eventper.png)
    Finally review and all the information and then click **Create schedule**.

After this, you can trigger the schedule and see the result in s3. The result can look like this:
   ![Pipeline](/images/5.pipeline/schedule.png)
    ![Pipeline](/images/5.pipeline/schedules.png)
Congratulations on completing the lab on creating a simple automated data pipeline that fetches data from an API and stores it in S3. Remember to perform resource cleanup to avoid unintended costs.