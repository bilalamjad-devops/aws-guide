
# 🧪 Lab 3: Failover Routing (High Availability)

📁 `route53/labs/lab3-failover/README.md`

## 🎯 Objective

Automatically switch to backup server if primary fails.

---

## 🏗️ Architecture

```id="y2k8vn"
Primary Server → fails ❌
       ↓
Route53 → Backup Server ✅
```

---

## 🚀 Steps

### Step 1: Create 2 Resources

* Primary (ALB / EC2)
* Secondary (backup)

---

### Step 2: Create Health Check

* Monitor primary server

---

### Step 3: Create Failover Records

* Primary record
* Secondary record

---

## ✅ Expected Outcome

* If primary fails → traffic goes to backup

---

## 🔐 Learning

👉 Used in:

* disaster recovery
* production systems

---

# 🎯 Final Understanding

Route 53 connects everything:

```id="z8p4tm"
Domain → Route53 → CloudFront / ALB → App
```

---

👉 Without Route 53:

* users cannot access your system properly

---

# 🧠 Big Picture (VERY IMPORTANT)

Now your full architecture is complete:

```id="u7x2kd"
User
 ↓
Route53
 ↓
CloudFront
 ↓
Load Balancer
 ↓
EKS / EC2
 ↓
App
 ↓
RDS / S3
```

---

👉 This is **real-world production architecture**

---
