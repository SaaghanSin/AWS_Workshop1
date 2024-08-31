---
title : "Create Lambda function"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 4.1. </b> "
---
**Create Lambda Function**
1. Go to [Lambda Console](https://ap-southeast-2.console.aws.amazon.com/lambda/home?region=ap-southeast-2#/functions)
   - Click **Create function**.

   ![Lambda](/images/3.lambda/lambda.png)

2. At the **Create bucket** page:
    - In the **Bucket name** field, write a meaningful name to identify this function, such as **Workshop1Function**.
    - In the **Runtime** field, choose the language use to write your function. In this workshop, I choose **Python 3.8** as we will need to import **request** - an external library.
     ![Lambda](/images/3.lambda/lambdac1.png)
    - In the **Permissions** field, choose **Use an existing role** from the **Execution role** option box. Then choose the role you have create in the preparation.
    - Review the information and then click **Create function**.
  - ![Lambda](/images/3.lambda/lambdac2.png)
  
3. (Optional) If this is your first time working with AWS Lambda, it’s a good idea to try something simple. Start with a **"Hello, World!"** program:

    ```python
    def lambda_handler(event, context):
        return {
            'statusCode': 200,
            'body': 'Hello, World!'
        }
    ```

   As you can see, the lambda_handler function is the entry point for AWS Lambda functions. When your Lambda function is invoked, AWS Lambda calls this function and passes it the event data and context. It conatain 2 parameters:
      - **event**:

         - This parameter contains data about the event that triggered the Lambda function. The structure of event depends on the source of the trigger (e.g., an API Gateway request, S3 event, etc.).
         - In this simple example, the event parameter is not used, but in more complex functions, it might contain request data, file information, or other relevant details.
      - **context**:

         - This parameter provides information about the runtime environment of the Lambda function, such as the function name, memory limits, and request identifiers.
         - Like event, context is not used in this example, but it can be useful for logging or accessing runtime information in more advanced scenarios.

   Let's continue on create Lambda layer to build our function.