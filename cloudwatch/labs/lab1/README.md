

## 📘 Lab 1: Monitor EC2 and Create a CPU Utilization Alarm

📁 `cloudwatch/labs/lab1-ec2-monitoring-alerts/README.md`

### 🎯 Objective

Monitor an EC2 instance and receive alerts when CPU usage exceeds a defined threshold.

### 🌍 Industry Use Case

Used by operations teams to detect performance issues and prevent downtime.

### 🏗️ Architecture

EC2 Instance → CloudWatch Metrics → CloudWatch Alarm → SNS → Email

### 📋 Prerequisites

* AWS account
* Running EC2 instance
* Configured SNS topic

### 🚀 Steps

1. Launch an EC2 instance.
2. Navigate to **CloudWatch → Alarms**.
3. Click **Create Alarm**.
4. Select **EC2 → CPUUtilization**.
5. Set threshold:

   * Type: Static
   * Value: **80%**
   * Period: 5 minutes.
6. Configure an SNS topic for notifications.
7. Enter your email and confirm the subscription.
8. Create the alarm.

### 🧪 Testing

Generate CPU load on the EC2 instance:

```bash
sudo yum install stress -y
stress --cpu 2 --timeout 300
```

### ✅ Expected Outcome

An email alert is triggered when CPU utilization exceeds 80%.

### 🔐 Best Practices

* Enable detailed monitoring.
* Use anomaly detection for production environments.
* Tag alarms for better management.

### 🧹 Cleanup

* Delete the CloudWatch alarm.
* Terminate the EC2 instance.

Commit Date: 19-April-2026
