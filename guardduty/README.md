
Great—**GuardDuty** is one of the most important services for AWS security. If you present it well, it shows you understand **threat detection + real security workflows**.

I’ll keep it **simple, practical, and industry-focused**, and I’ll use **EventBridge / CloudWatch terms properly (not overused)**.

---

# 📁 Folder Structure

```plaintext
aws-guide/
└── guardduty/
    ├── README.md
    └── labs/
        ├── lab1-enable-guardduty/
        ├── lab2-detect-ec2-threat/
        ├── lab3-iam-credential-exposure/
        └── lab4-automated-response-eventbridge/
```

---

# 📘 guardduty/README.md

# AWS GuardDuty

Amazon GuardDuty is a threat detection service by Amazon Web Services that continuously monitors your AWS account for malicious activity and unauthorized behavior.

---

## 📌 Overview (Simple)

GuardDuty answers:

> “Is something suspicious happening in my AWS account?”

It analyzes:

* CloudTrail logs
* VPC Flow Logs
* DNS logs

👉 Without installing anything.

---

## 🚀 Key Features

* Continuous threat detection
* No agents required
* Detects compromised instances
* Detects suspicious IAM activity
* Built-in threat intelligence (malicious IPs, domains)
* Severity levels (Low / Medium / High / Critical)
* Integration with other AWS services

---

## 🔍 What GuardDuty Detects

| Category            | Example                         |
| ------------------- | ------------------------------- |
| EC2 Threats         | Crypto mining, bot activity     |
| IAM Issues          | Unusual API calls               |
| Credential Exposure | Access keys leaked              |
| Network Threats     | Communication with malicious IP |

---

## 🔐 Security Best Practices

* Enable GuardDuty in all regions
* Review **High/Critical findings first**
* Integrate with AWS Security Hub
* Automate alerts using EventBridge
* Do not ignore repeated findings
* Use least privilege IAM

---

## 🌍 Real-World Use Cases

* Detect compromised EC2 instances
* Identify leaked AWS credentials
* Monitor suspicious API activity
* Detect communication with malicious IPs
* Support SOC and incident response

---

## 🏗️ Architecture (Simple)

```plaintext
Logs (CloudTrail / VPC / DNS)
        ↓
GuardDuty (Detection)
        ↓
EventBridge (Trigger)
        ↓
SNS / Lambda (Alert / Action)
```

---

## ⭐ Why it matters

* Real-time threat detection
* No manual setup
* Core service for DevSecOps
* Used in almost every secure AWS environment

---

## 📚 References

* [https://docs.aws.amazon.com/guardduty/](https://docs.aws.amazon.com/guardduty/)
* [https://aws.amazon.com/guardduty/](https://aws.amazon.com/guardduty/)

---

# 🧪 LABS (Real-World & Practical)

---

# 🔬 Lab 1: Enable GuardDuty

📁 `lab1-enable-guardduty/README.md`

## 🎯 Objective

Enable GuardDuty and start monitoring your AWS account.

---

## 🌍 Real-World Scenario

A company wants:

> “Basic threat detection enabled in AWS”

---

## 🪜 Steps

1. Go to GuardDuty console
2. Click **Enable GuardDuty**
3. Select region (repeat for all regions later)

---

## ✅ Result

GuardDuty starts analyzing logs automatically.

---

## 🧠 Real Meaning

> “Security monitoring is now active”

---

---

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

---

# 🔥 Big Understanding (VERY IMPORTANT)

Think like this:

```plaintext
GuardDuty = Detect threat
EventBridge = Trigger action
SNS/Lambda = Response
```

---

# 🚀 Why this makes your profile strong

This shows:

* ✅ You understand **real threat detection**
* ✅ You can build **automated security workflows**
* ✅ You think like a **security engineer, not just learner**
* ✅ You know how AWS services work together

---

# 🎯 Next Step (Recommended)

Now you have strong security stack:

* CloudTrail (logs)
* CloudWatch (monitoring)
* GuardDuty (detection)
* Detective (investigation)
* Inspector (vulnerabilities)

👉 Next best service:

* Security Hub (central dashboard)

---

If you want, I can next:

* Create **Security Hub complete guide (very powerful final piece)**
* Or help you convert this into a **top-quality Medium article with diagrams**


Commit Date: 19-April-2026
