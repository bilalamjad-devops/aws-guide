

## 🧪 Lab 2: Automate Notifications Using SNS and AWS Lambda

📁 `sns/labs/lab2-sns-with-lambda/README.md`

# Lab 2: Trigger AWS Lambda Using Amazon SNS

## 🎯 Objective

Learn how to invoke an AWS Lambda function using Amazon SNS.

## 📋 Prerequisites

* Basic knowledge of AWS Lambda
* IAM permissions for SNS and Lambda

## 🏗️ Architecture

```
SNS Topic → AWS Lambda → CloudWatch Logs
```

## 🚀 Steps

### Step 1: Create an SNS Topic

1. Navigate to **Amazon SNS**.
2. Create a topic named `SNS-Lambda-Topic`.

### Step 2: Create a Lambda Function

1. Open the **AWS Lambda Console**.
2. Click **Create function**.
3. Select **Author from scratch**.
4. Function name: `SNSDemoFunction`.
5. Runtime: **Python 3.x**.
6. Click **Create function**.

### Step 3: Add Lambda Code

Replace the default code with:

```python
import json

def lambda_handler(event, context):
    for record in event['Records']:
        message = record['Sns']['Message']
        print("Message received from SNS:", message)
    
    return {
        'statusCode': 200,
        'body': json.dumps('SNS message processed successfully!')
    }
```

Click **Deploy**.

### Step 4: Subscribe Lambda to the SNS Topic

1. Open the SNS topic.
2. Click **Create subscription**.
3. Select protocol **AWS Lambda**.
4. Choose `SNSDemoFunction`.
5. Click **Create subscription**.

### Step 5: Test the Integration

1. Publish a message to the SNS topic.
2. Go to **CloudWatch Logs**.
3. Verify that the Lambda function was triggered.

## ✅ Expected Outcome

The Lambda function processes the SNS message and logs it in CloudWatch.

## 🔐 Security Best Practices

* Use IAM roles with least privilege.
* Enable encryption with AWS KMS.
* Monitor logs with CloudWatch.
* Restrict topic access using resource policies.

## 🧹 Cleanup

* Delete the Lambda function.
* Delete the SNS topic.
* Remove CloudWatch log groups.

---

## 🚀 How to Use This Content

* Upload it to your **aws-guide** GitHub repository.
* Convert each lab into a Medium article.
* Add architecture diagrams using Draw.io.
* Share your work on LinkedIn and with the AWS community.

If you'd like, I can also generate Terraform scripts for these labs to align with DevSecOps practices.
