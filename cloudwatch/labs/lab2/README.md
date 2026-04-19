

## 📘 Lab 2: Monitor AWS Lambda Logs Using CloudWatch Logs

📁 `cloudwatch/labs/lab2-cloudwatch-logs-lambda-monitoring/README.md`

### 🎯 Objective

Analyze and monitor Lambda logs using CloudWatch Logs and Log Insights.

### 🌍 Industry Use Case

Used by DevOps teams for troubleshooting and observability in serverless applications.

### 🏗️ Architecture

AWS Lambda → CloudWatch Logs → Log Insights

### 🚀 Steps

1. Create a Lambda function using Python.
2. Add the following code:

```python
import json

def lambda_handler(event, context):
    print("CloudWatch monitoring demonstration.")
    return {
        'statusCode': 200,
        'body': json.dumps('Success')
    }
```

3. Deploy and invoke the function.
4. Navigate to **CloudWatch → Log Groups**.
5. Open `/aws/lambda/<function-name>`.

### 🔍 Query Logs Using Log Insights

```sql
fields @timestamp, @message
| sort @timestamp desc
| limit 20
```

### ✅ Expected Outcome

Lambda logs are visible and searchable in CloudWatch.

### 🔐 Best Practices

* Configure log retention policies.
* Encrypt logs using AWS KMS.
* Monitor errors and latency.

### 🧹 Cleanup

* Delete the Lambda function.
* Remove log groups.

Commit Date: 19-April-2026
