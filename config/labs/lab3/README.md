

---

# 🔬 Lab 3: Monitor EC2 Security Compliance

📁 `lab3-ec2-compliance-monitoring/README.md`

## 🎯 Objective

Ensure EC2 instances follow security rules.

---

## 🌍 Real-World Scenario

> “No EC2 should have open SSH (0.0.0.0/0)”

---

## 🪜 Steps

### Step 1: Enable rule

Use managed rule:

* `restricted-ssh`

---

### Step 2: Create violation

* Open port 22 to:

```plaintext id="1yyo4p"
0.0.0.0/0
```

---

### Step 3: Check Config

* Go to Config → Rules
* See NON_COMPLIANT

---

## ✅ Result

Rule detects open SSH access.

---

## 🧠 Real Meaning

> “Prevent insecure network exposure”

---
