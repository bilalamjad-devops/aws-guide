

Great—**AWS Detective** is exactly what shows you understand **incident investigation**, not just detection. I’ll keep it simple, practical, and aligned with real security workflows.

---

# 📁 Folder Structure

```plaintext id="2v8f0o"
aws-guide/
└── detective/
    ├── README.md
    └── labs/
        ├── lab1-enable-detective/
        ├── lab2-investigate-iam-activity/
        ├── lab3-ec2-suspicious-traffic/
        └── lab4-automated-alerting-eventbridge/
```

---

# 📘 detective/README.md

# AWS Detective

Amazon Detective is a security investigation service by Amazon Web Services that helps analyze, investigate, and understand security findings in AWS.

---

## 📌 Overview (Simple)

If:

* Amazon GuardDuty **detects a threat**

Then:

* Amazon Detective helps you answer:

> “What exactly happened? Who did it? How?”

👉 Think:

```plaintext
GuardDuty = Detect problem
Detective = Investigate problem
```

---

## 🚀 Key Features

* Automatic data collection (no manual setup)
* Visual investigation graphs
* Timeline analysis of activity
* Behavior analysis (users, IPs, instances)
* Integration with GuardDuty and Security Hub
* Root cause analysis

---

## 🔍 What Detective Analyzes

| Area          | Example              |
| ------------- | -------------------- |
| IAM Users     | Suspicious API calls |
| EC2 Instances | Unusual traffic      |
| IP Addresses  | Malicious activity   |
| API Activity  | Unauthorized actions |

---

## 🔐 Security Best Practices

* Enable Detective in all regions
* Integrate with AWS Security Hub
* Investigate all **High severity findings**
* Combine with GuardDuty for detection
* Use IAM least privilege
* Maintain logs using CloudTrail

---

## 🌍 Real-World Use Cases

* Investigating compromised IAM users
* Analyzing suspicious EC2 traffic
* Understanding attack timelines
* Root cause analysis after incidents
* Supporting SOC teams

---

## 🏗️ Architecture (Simple)

```plaintext id="p0a4s1"
CloudTrail / VPC Logs → GuardDuty → Detective → Investigation
                                  ↓
                         EventBridge → SNS / Lambda Alerts
```

---

## ⭐ Why it matters

* Moves you from **monitoring → investigation**
* Helps in real incident response
* Used by SOC and security teams

---

## 📚 References

* [https://docs.aws.amazon.com/detective/](https://docs.aws.amazon.com/detective/)
* [https://aws.amazon.com/detective/](https://aws.amazon.com/detective/)

---

# 🧪 LABS (Real-World & Industry)

---


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

# 🔥 Big Understanding (IMPORTANT)

```plaintext id="9rj2qg"
GuardDuty → Detect threat
Detective → Investigate
EventBridge → Respond
```

---

# 🚀 Why This is Powerful for You

This shows recruiters:

* ✅ You understand **incident response lifecycle**
* ✅ Not just alerts, but **investigation**
* ✅ You know **real security workflows**
* ✅ You can build **automated security systems**

---

# 🎯 Next Best Step

After this, you should cover:

* Security Hub (central dashboard)
* GuardDuty (deep detection)
* IAM (most important)

---

If you want, next I can:

* Convert this into a **Medium article (very strong one)**
* Or create a **complete security architecture diagram (for all services together)**


Commit Date: 19-April-2026
