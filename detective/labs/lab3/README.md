


# 🔬 Lab 3: Investigate EC2 Suspicious Traffic

📁 `lab3-ec2-suspicious-traffic/README.md`

## 🎯 Objective

Analyze unusual EC2 network activity.

---

## 🌍 Real-World Scenario

> “EC2 instance communicating with unknown IP”

---

## 🪜 Steps

### Step 1: Generate traffic

* SSH into EC2
* Use curl:

```bash id="y1s8lq"
curl http://example.com
```

---

### Step 2: Trigger GuardDuty finding

* Simulate unusual activity (repeated requests)

---

### Step 3: Investigate in Detective

* Open EC2 entity
* View:

  * Connections
  * Remote IPs
  * Traffic patterns

---

## ✅ Result

You see:

* Communication patterns
* External IPs

---

## 🧠 Real Meaning

> “Detect compromised server behavior”

---

---
