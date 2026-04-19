


# 🔬 Lab 4: Automated Alerting using EventBridge

📁 `lab4-automated-alerting-eventbridge/README.md`

## 🎯 Objective

Automatically respond to security findings.

---

## 🌍 Real-World Scenario

> “When threat detected → notify team immediately”

---

## 🧩 Flow

GuardDuty → EventBridge → SNS / Lambda → Alert

---

## 🪜 Steps

### Step 1: Create EventBridge Rule

* Go to EventBridge
* Create rule

Event pattern:

```json id="2clqj7"
{
  "source": ["aws.guardduty"],
  "detail-type": ["GuardDuty Finding"]
}
```

---

### Step 2: Set Target

* SNS (email alert)
  OR
* Lambda (custom action)

---

### Step 3: Test

* Trigger GuardDuty finding

---

## ✅ Result

* Instant alert sent

---

## 🧠 Real Meaning

> “Security becomes real-time and automated”

---

---
