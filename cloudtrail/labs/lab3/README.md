

## 🔬 Lab 3: Monitor AWS Console Login Activity

📁 `cloudtrail/labs/lab3-monitor-console-logins/README.md`

### 🎯 Objective

Track successful and failed console login attempts.

### 🌍 Industry Use Case

SOC teams monitor login behavior to detect unauthorized access.

### 🏗️ Architecture

CloudTrail → CloudWatch Logs → SNS

### 🚀 Steps

1. Send CloudTrail logs to CloudWatch.
2. Create a metric filter:

   ```
   { $.eventName = ConsoleLogin }
   ```
3. For failed logins:

   ```
   { $.eventName = ConsoleLogin && $.errorMessage = "Failed authentication" }
   ```
4. Create an alarm and configure SNS notifications.

### 🧪 Testing

Attempt a login with incorrect credentials.

### ✅ Expected Outcome

An alert is sent when a login attempt occurs.

---
