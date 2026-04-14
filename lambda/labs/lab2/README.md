

---

## 🧪 Lab 2: Send AWS Lambda Notifications to Slack

📁 `lambda/labs/lab2-lambda-slack-notifications/README.md`

# Lab 2: Send AWS Lambda Alerts to Slack

## Objective

Send real-time alerts from AWS Lambda to a Slack channel using a webhook.

## Real-World Scenario

DevOps and security teams receive alerts in Slack for incidents such as deployment failures, security findings, and system anomalies.

## Architecture

AWS Lambda → Slack Webhook → Slack Channel

## Prerequisites

* AWS account
* A Slack workspace
* Incoming Webhook URL from Slack

## Step 1: Create a Slack Incoming Webhook

1. Visit: [https://api.slack.com/apps](https://api.slack.com/apps)
2. Click **Create New App**.
3. Choose **From Scratch**.
4. Enable **Incoming Webhooks**.
5. Add a webhook to your channel.
6. Copy the webhook URL.

## Step 2: Create a Lambda Function

1. Open AWS Lambda Console.
2. Click **Create function**.
3. Function Name: `SlackNotifier`.
4. Runtime: **Python 3.x**.
5. Click **Create function**.

## Step 3: Add Environment Variable

* Key: `SLACK_WEBHOOK_URL`
* Value: Paste your webhook URL.

## Step 4: Add Lambda Code

```python
import json
import os
import urllib3

http = urllib3.PoolManager()

def lambda_handler(event, context):
    webhook_url = os.environ['SLACK_WEBHOOK_URL']
    
    message = {
        "text": "🚀 AWS Lambda Alert: Function executed successfully!"
    }

    encoded_msg = json.dumps(message).encode("utf-8")
    
    response = http.request(
        "POST",
        webhook_url,
        body=encoded_msg,
        headers={"Content-Type": "application/json"}
    )

    return {
        "statusCode": response.status,
        "body": "Notification sent to Slack!"
    }
```

Click **Deploy**.

## Step 5: Test the Function

1. Click **Test** in the Lambda console.
2. Create a test event and execute the function.
3. Verify the message in Slack.

## Expected Outcome

A notification is delivered to the Slack channel in real time.

## Security Best Practices

* Store the webhook URL in AWS Secrets Manager for production.
* Avoid hardcoding credentials.
* Restrict IAM permissions.
* Monitor execution with CloudWatch Logs.

## Cleanup

* Delete the Lambda function.
* Remove the Slack webhook.

---

## 🚀 How This Strengthens Your Portfolio

* Demonstrates expertise in serverless computing.
* Showcases real-world DevOps automation.
* Highlights third-party integrations.
* Aligns with DevSecOps best practices.
* Enhances your Medium articles and GitHub profile.

If you'd like, I can also:

* Generate Terraform scripts for these labs, or
* Prepare Medium-ready articles with diagrams and screenshots.


Commit Date: 15-April-2026

