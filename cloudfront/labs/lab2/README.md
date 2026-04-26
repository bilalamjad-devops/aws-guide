# 🧪 Lab 2: CloudFront with ALB (Dynamic App)

📁 `cloudfront/labs/lab2-cloudfront-alb/README.md`

## 🎯 Objective

Use CloudFront in front of your application (ALB).

---

## 🏗️ Architecture

```id="z6k3bn"
User → CloudFront → ALB → EC2 / EKS
```

---

## 🚀 Steps

### Step 1: Create ALB

* Attach EC2 / EKS app

---

### Step 2: Create CloudFront

* Origin: ALB DNS
* Enable caching (optional for API)

---

### Step 3: Access App

```id="g2v7qe"
https://<cloudfront-domain>
```

---

## ✅ Expected Outcome

* Faster response
* Reduced load on backend

---

## 🔐 Learning

👉 This is real production architecture

---
