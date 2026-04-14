

## 🧪 Lab 1: Trigger AWS Lambda from Amazon S3

📁 `lambda/labs/lab1-s3-trigger-lambda/README.md`

# Lab 1: Process File Uploads Using AWS Lambda and Amazon S3

## Objective

Automatically trigger a Lambda function when a file is uploaded to an S3 bucket.

## Real-World Scenario

Organizations use this architecture to process uploaded documents, images, and logs in real time.

## Architecture

S3 Bucket → AWS Lambda → CloudWatch Logs

## Prerequisites

* AWS account
* IAM permissions for Lambda and S3
* Basic knowledge of Python

## Step 1: Create an S3 Bucket

1. Open the S3 Console.
2. Click **Create bucket**.
3. Enter a unique name: `lambda-s3-trigger-bucket`.
4. Click **Create bucket**.

## Step 2: Create a Lambda Function

1. Open the AWS Lambda Console.
2. Click **Create function**.
3. Choose **Author from scratch**.
4. Function Name: `S3FileProcessor`.
5. Runtime: **Python 3.x**.
6. Click **Create function**.

## Step 3: Add Lambda Code

```python
import json

def lambda_handler(event, context):
    for record in event['Records']:
        bucket = record['s3']['bucket']['name']
        file_name = record['s3']['object']['key']
        print(f"File '{file_name}' uploaded to bucket '{bucket}'")
    
    return {
        'statusCode': 200,
        'body': json.dumps('File processed successfully!')
    }
```

Click **Deploy**.

## Step 4: Configure the S3 Trigger

1. Navigate to the Lambda function.
2. Click **Add Trigger**.
3. Select **S3**.
4. Choose the created bucket.
5. Select event type: **PUT**.
6. Click **Add**.

## Step 5: Test the Solution

1. Upload a file to the S3 bucket.
2. Open **CloudWatch Logs**.
3. Verify the log output.

## Expected Outcome

The Lambda function is automatically triggered upon file upload.

## Security Best Practices

* Grant least-privilege IAM permissions.
* Enable S3 encryption.
* Enable CloudTrail for auditing.

## Cleanup

* Delete the Lambda function.
* Delete the S3 bucket.

---



Commit Date: 15-April-2026

