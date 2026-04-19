

---

# 🔬 Lab 4: Auto Remediation using EventBridge

📁 `lab4-auto-remediation-eventbridge/README.md`

## 🎯 Objective

Automatically respond to non-compliant resources.

---

## 🌍 Real-World Scenario

> “If S3 becomes public → alert or fix automatically”

---

## 🧩 Flow

AWS Config → EventBridge → Lambda / SNS

---

## 🪜 Steps

### Step 1: Create EventBridge Rule

Event pattern:

```json id="1h1a9i"
{
  "source": ["aws.config"],
  "detail-type": ["Config Rules Compliance Change"]
}
```

---

### Step 2: Set Target

* SNS → alert
  OR
* Lambda → auto fix (remove public access)

---

### Step 3: Test

* Make S3 bucket public

---

## ✅ Result

* Alert triggered OR
* Auto remediation executed

---

## 🧠 Real Meaning

> “Compliance becomes automatic”

---

---
