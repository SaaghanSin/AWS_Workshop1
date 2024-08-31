---
title : "Create Function Layer"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 4.2. </b> "
---

**Create Function Layer**


1. Go to [Function Console](https://ap-southeast-2.console.aws.amazon.com/lambda/home?region=ap-southeast-2#/functions)
   - In the **Additional resouces** Click **Layers**.
   - The **Layers Console** page show up. Then click **Create layers**.

   ![Lambda](/images/3.lambda/layer.png)

2. At the **Create layers** page:
   - In the **Layer name** field, write a meaningful name to identify this function, such as **pythonRequests**.
   - Click **Upload** then upload the **Request** library you have download before to upload to AWS Layer.
   - In the **Runtime** field, to omit the unwant situation, choose the runtime compatible with your function runtime.
   - Review the information and then click **Create**.
  
     ![Lambda](/images/3.lambda/layerc.png)

After creating the layer, proceed to the next step to import the layer into your function.