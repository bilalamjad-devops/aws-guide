
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

## Lab 4 in Simple

---

# 🔬 Lab 4 (Simple): Detect Unusual Activity (Smart Detection)

### 🧠 What is the idea?

Instead of rules, AWS detects:

> “This activity looks unusual”

Example:

* Suddenly 100 API calls
* Too many EC2 actions

---

## 🧩 Flow

CloudTrail Insights → CloudWatch → Alert

---

## 🪜 Steps

### Step 1: Enable Insights

* Go to CloudTrail
* Edit Trail
* Enable **Insights**
* Select: Write events

---

### Step 2: Wait or Generate Activity

👉 Do this:

* Start/stop EC2 many times
* Repeat actions quickly

---

## ✅ Result

AWS says:

> “Unusual API activity detected”

---

## 🧠 Real-world meaning

> “Something abnormal is happening (possible attack or script misuse)”

---

---

Commit Date: 19-April-2026
