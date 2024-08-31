---
title : "Create S3 Bucket"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 3. </b> "
---

In this step, we will create a S3 storage to store our data.

1. Go to [Amazon S3](https://ap-southeast-2.console.aws.amazon.com/s3/home?region=ap-southeast-2#)
   - Click **CreateBucket**.

   ![S3](/images/4.s3/s3.png)

2. At the **Create bucket** page:
    - In the **Bucket name** field, write a meaningful name to identify this bucket, such as **Workshop1Bucket**.
    - At the **Block Public Access** setting, you won't want other people access to your bucket. So for now just choose **Block all public access**.
    - Review the create S3 Bucket information and then click **Create bucket**.
  
   ![S3](/images/4.s3/BPA.png)

For now, let's continue to make lambda function.