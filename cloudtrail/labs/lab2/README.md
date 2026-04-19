


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

## Lab 2 in Simple 

# 🔬 Lab 2 (Simple): Detect Security Group Changes

### 🧠 What is the idea?

If **someone opens a port (like 22 or 80)** in a security group → you should get an alert.

👉 This is important because attackers often open ports.

---

## 🧩 Flow (very simple)

AWS CloudTrail → Amazon CloudWatch → Alarm → Amazon Simple Notification Service (Email)

---

## 🪜 Steps (easy)

### Step 1: Send logs to CloudWatch

* Go to CloudTrail
* Open your Trail
* Enable **CloudWatch Logs integration**

👉 Now all activity logs go to CloudWatch

---

### Step 2: Create filter (this is key)

Go to CloudWatch → Log Groups → CloudTrail log group

Create **Metric Filter**:

```
{ $.eventName = AuthorizeSecurityGroupIngress }
```

👉 Meaning:

> “Detect when someone changes security group rules”

---

### Step 3: Create Alarm

* Use this metric
* Set condition: ≥ 1
* Connect to SNS (email)

---

### Step 4: Test

* Go to EC2
* Edit security group
* Add a rule (like port 80)

---

## ✅ Result

You get an **email alert**

---

## 🧠 Real-world meaning

> “If someone opens a port in production → I get alert instantly”

---


