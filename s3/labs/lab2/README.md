

# 🧪 Lab 2: Store Logs (Real DevOps Use Case)

📁 `s3/labs/lab2-store-logs/README.md`

## 🎯 Objective

Store logs in S3 (CloudTrail / ALB logs).

---

## 🏗️ Architecture

```id="c9t2wr"
AWS Service → S3 Bucket (logs)
```

---

## 🚀 Steps

### Step 1: Create Bucket

* Name: `my-log-bucket`
* Keep private

---

### Step 2: Enable CloudTrail Logging

* Go to CloudTrail
* Create trail
* Select S3 bucket

---

### Step 3: Verify Logs

* Open S3
* Check logs folder

---

## ✅ Expected Outcome

* Logs stored automatically

---

## 🔐 Learning

👉 All production systems store logs in S3

---
