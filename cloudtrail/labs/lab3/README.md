

## 🔬 Lab 2: Detect Unauthorized API Activity Using CloudTrail

📁 `cloudtrail/labs/lab2-detect-unauthorized-api-activity/README.md`

### 🎯 Objective

Monitor and identify unauthorized actions such as security group changes.

### 🌍 Industry Use Case

Security teams detect misconfigurations and suspicious activity.

### 🏗️ Architecture

CloudTrail → CloudWatch Logs → Alarm → SNS

### 🚀 Steps

1. Integrate CloudTrail with CloudWatch Logs.
2. Create a metric filter using the following pattern:

   ```
   { $.eventName = AuthorizeSecurityGroupIngress }
   ```
3. Create a CloudWatch alarm.
4. Configure an SNS topic for notifications.

### 🧪 Testing

Modify a security group rule.

### ✅ Expected Outcome

An alert is triggered when a security group is modified.

---
