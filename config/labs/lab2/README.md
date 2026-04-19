

# 🔬 Lab 2: Detect Public S3 Buckets

📁 `lab2-s3-public-access-check/README.md`

## 🎯 Objective

Detect if any S3 bucket becomes public.

---

## 🌍 Real-World Scenario

> “Public S3 bucket → major security risk”

---

## 🪜 Steps

### Step 1: Enable rule

Go to Config → Rules

Select managed rule:

* `s3-bucket-public-read-prohibited`

---

### Step 2: Create test bucket

* Create S3 bucket
* Enable public access

---

### Step 3: Check compliance

* Go to Config → Rules
* See status: **NON_COMPLIANT**

---

## ✅ Result

AWS Config flags the bucket.

---

## 🧠 Real Meaning

> “System detects risky configuration automatically”

---
