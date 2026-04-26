
# 🧪 Lab 2: Route53 with CloudFront (Production Setup)

📁 `route53/labs/lab2-cloudfront-domain/README.md`

## 🎯 Objective

Connect domain with CloudFront.

---

## 🏗️ Architecture

```id="t6k1pz"
User → Route53 → CloudFront → S3 / ALB
```

---

## 🚀 Steps

### Step 1: Create CloudFront Distribution

* Origin: S3 or ALB

---

### Step 2: Add Custom Domain

* Add `www.example.com`
* Attach SSL (ACM certificate)

---

### Step 3: Create Route53 Record

* Type: A (Alias)
* Target: CloudFront

---

## ✅ Expected Outcome

```id="w9m3xa"
www.example.com → CloudFront → fast + secure
```

---

## 🔐 Learning

👉 This is MOST COMMON production architecture

---


