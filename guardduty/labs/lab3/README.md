


# 🔬 Lab 3: Detect IAM Credential Exposure

📁 `lab3-iam-credential-exposure/README.md`

## 🎯 Objective

Understand how GuardDuty detects leaked credentials.

---

## 🌍 Real-World Scenario

> “AWS access keys leaked on GitHub”

---

## 🪜 Steps (Safe Simulation)

Instead of real leak:

1. Create IAM user with access key
2. Use key from unusual location (VPN / different IP)

---

### Step 2: Generate API activity

Run AWS CLI commands:

* List S3 buckets
* Create resources

---

### Step 3: Check GuardDuty

* Look for unusual access pattern findings

---

## ✅ Result

GuardDuty flags suspicious API usage.

---

## 🧠 Real Meaning

> “Credentials might be stolen”

---

---
