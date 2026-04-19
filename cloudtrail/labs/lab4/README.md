
## 🔬 Lab 4: Detect Anomalies Using CloudTrail Insights

📁 `cloudtrail/labs/lab4-cloudtrail-security-automation/README.md`

### 🎯 Objective

Detect unusual API activity using CloudTrail Insights.

### 🌍 Industry Use Case

Used by enterprise security teams for threat detection and behavioral analysis.

### 🏗️ Architecture

CloudTrail Insights → CloudWatch → SNS

### 🚀 Steps

1. Navigate to **CloudTrail → Trails**.
2. Edit the trail.
3. Enable **CloudTrail Insights**.
4. Select **Write Management Events**.
5. Save changes.

### 🧪 Testing

Simulate unusual API activity by repeatedly starting and stopping EC2 instances.

### ✅ Expected Outcome

CloudTrail Insights detects anomalies and generates alerts.

---

Commit Date: 19-April-2026
