

# 🔬 Lab 2: Detect Suspicious EC2 Activity

📁 `lab2-detect-ec2-threat/README.md`

## 🎯 Objective

Simulate suspicious EC2 behavior and observe GuardDuty detection.

---

## 🌍 Real-World Scenario

> “Server starts communicating with unknown or malicious IP”

---

## 🪜 Steps

### Step 1: Launch EC2

* Use Amazon Linux

---

### Step 2: Generate traffic

SSH into EC2:

```bash
curl http://example.com
```

Repeat multiple times or use external IPs.

---

### Step 3: Wait for detection

* GuardDuty analyzes traffic

---

### Step 4: Check Findings

* Go to GuardDuty → Findings

---

## ✅ Result

You may see:

* Suspicious outbound traffic
* Unusual behavior alerts

---

## 🧠 Real Meaning

> “Server may be compromised or misused”

---

---
