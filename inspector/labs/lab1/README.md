

# 🔬 Lab 1: Scan EC2 for Vulnerabilities

📁 `lab1-enable-inspector-ec2/README.md`

## 🎯 Objective

Scan an EC2 instance for vulnerabilities and identify risky packages.

---

## 🌍 Real-World Scenario

A company wants to check:

> “Are our servers running outdated or vulnerable software?”

---

## 🪜 Steps

### Step 1: Launch EC2

* Use Amazon Linux / Ubuntu

---

### Step 2: Enable Inspector

* Go to **Amazon Inspector**
* Click **Enable**

👉 It auto-detects EC2

---

### Step 3: Wait for scan

* Takes a few minutes

---

### Step 4: View Findings

* Go to **Findings**
* Check:

  * CVE ID
  * Severity (High/Critical)
  * Affected package

---

## ✅ Result

You will see vulnerabilities like:

* Outdated packages
* Known CVEs

---

## 🧠 Real Meaning

> “Your server is not secure → update required”

---

## 🔐 Best Practice

* Always patch EC2 regularly
* Focus on **Critical findings first**

---

---
