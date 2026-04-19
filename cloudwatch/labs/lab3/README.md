

## 📘 Lab 3: Security Alerts Using CloudWatch and SNS

📁 `cloudwatch/labs/lab3-security-alerts-sns/README.md`

### 🎯 Objective

Send real-time alerts for security-related events using CloudWatch and SNS.

### 🌍 Industry Use Case

Security teams receive alerts for unauthorized access attempts or suspicious activity.

### 🏗️ Architecture

CloudTrail → CloudWatch Logs → Metric Filter → Alarm → SNS → Email

### 📋 Prerequisites

* AWS CloudTrail enabled
* SNS topic configured

### 🚀 Steps

1. Enable CloudTrail and send logs to CloudWatch.
2. Navigate to **CloudWatch → Log Groups**.
3. Select the CloudTrail log group.
4. Create a **Metric Filter** with the following pattern:

```plaintext
{ $.eventName = ConsoleLogin && $.errorMessage = "Failed authentication" }
```

5. Create a metric named `FailedConsoleLogins`.
6. Create an alarm for this metric.
7. Configure SNS notifications.

### 🧪 Testing

Attempt a failed login using incorrect credentials.

### ✅ Expected Outcome

An alert email is sent when a failed login attempt occurs.

### 🔐 Best Practices

* Integrate with AWS Security Hub.
* Forward alerts to Slack for real-time response.
* Automate remediation using AWS Lambda.

### 🧹 Cleanup

* Delete alarms and metric filters.
* Remove SNS topics if no longer needed.

Commit Date: 19-April-2026
