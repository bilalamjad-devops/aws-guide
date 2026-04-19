


# 🔬 Lab 4: Automated Response using EventBridge

📁 `lab4-automated-response-eventbridge/README.md`

## 🎯 Objective

Automatically respond to GuardDuty findings.

---

## 🌍 Real-World Scenario

> “When threat detected → notify team instantly”

---

## 🧩 Flow

GuardDuty → EventBridge → SNS / Lambda

---

## 🪜 Steps

### Step 1: Create EventBridge Rule

Go to EventBridge → Create Rule

Event pattern:

```json
{
  "source": ["aws.guardduty"],
  "detail-type": ["GuardDuty Finding"]
}
```

---

### Step 2: Set Target

* SNS → Email alert
  OR
* Lambda → Custom action (tag EC2, stop instance)

---

### Step 3: Test

* Trigger any GuardDuty finding

---

## ✅ Result

* Alert sent instantly
* Or automated action executed

---



## 🧠 Real Meaning

> “Security is automated, not manual”

---
