---
title : "Creating Lambda Function Content"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 4.4. </b> "
---

**Creating Lambda Function Content**
We have set up the enviroment for our function.  Now, let’s look at the content of the Lambda function in this workshop:
```python
import requests
import json
import boto3
from datetime import datetime

s3_client = boto3.client("s3")


def fetch_data_and_store_to_s3(object_name, bucket_name):
    base_url = f"https://api.spacexdata.com/v3/{object_name}"
    offset = 0
    limit = 10
    while True:
        url = f"{base_url}?limit={limit}&offset={offset}"
        response = requests.get(url, timeout=10)
        data = response.json()
        if not data:
            break
        store_to_s3(data, bucket_name, object_name, offset, limit)
        offset += limit


def store_to_s3(data, bucket_name, object_name, offset, limit):
    timestamp = datetime.utcnow().strftime("%Y%m%d%H%M%S")
    file_name = f"spacex/{object_name}/{object_name}_offset_{offset}_{timestamp}.json"
    s3_client.put_object(Bucket=bucket_name, Key=file_name, Body=json.dumps(data))


def lambda_handler(event, context):
    object_name = "capsules"
    bucket_name = "spacex-fpt-bucket"
    fetch_data_and_store_to_s3(object_name, bucket_name)
    object_name = "cores"
    fetch_data_and_store_to_s3(object_name, bucket_name)
    return {
        "statusCode": 200,
        "body": json.dumps({"message": "Data fetched and stored to S3 successfully"}),
    }

```

The Lambda function is designed to automate the process of fetching data from the SpaceX API and storing it in Amazon S3. It handles pagination to manage large datasets, ensures each file is uniquely named with a timestamp, and provides a clear response upon successful completion. This setup allows for efficient data collection and storage without manual intervention.