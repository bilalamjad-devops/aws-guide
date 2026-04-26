
# 🧪 Lab 1: Connect Domain to Load Balancer

📁 `route53/labs/lab1-domain-alb/README.md`

## 🎯 Objective

Connect your domain to an ALB.

---

## 🏗️ Architecture

```id="p3k9we"
User → Route53 → ALB → EC2 / EKS
```

---

## 🚀 Steps

### Step 1: Create Hosted Zone

* Go to Route 53
* Create hosted zone: `example.com`

---

### Step 2: Update Domain Nameservers

* Copy NS records
* Update in domain provider

---

### Step 3: Create Record

* Type: **A (Alias)**
* Target: ALB DNS

---

## ✅ Expected Outcome

```id="q7n2ka"
example.com → your application
```

---

## 🔐 Learning

👉 Real production apps use domain + ALB

---
