
---

## 🔬 Lab 1: Enable AWS CloudTrail and Store Logs in S3

📁 `cloudtrail/labs/lab1-enable-cloudtrail/README.md`

### 🎯 Objective

Enable CloudTrail to capture API activity across your AWS account.

### 🌍 Industry Use Case

Organizations use CloudTrail to meet compliance and auditing requirements.

### 🏗️ Architecture

AWS Account → CloudTrail → Amazon S3

### 🚀 Steps

1. Sign in to the AWS Management Console.
2. Navigate to **CloudTrail**.
3. Click **Create Trail**.
4. Enter the trail name: `organization-trail`.
5. Select **Multi-region trail**.
6. Create a new S3 bucket.
7. Enable **Log File Validation**.
8. Enable **KMS Encryption**.
9. Click **Create Trail**.

### ✅ Expected Outcome

All API activities are recorded and stored securely in Amazon S3.

### 🧹 Cleanup

Delete the trail and S3 bucket if no longer required.

---
