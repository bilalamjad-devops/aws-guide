
# 🧪 Lab 1: CloudFront with S3 (Static Website)

📁 `cloudfront/labs/lab1-s3-cloudfront/README.md`

## 🎯 Objective

Host a static website using S3 + CloudFront.

---

## 🏗️ Architecture

```id="c1p8zd"
User → CloudFront → S3
```

---

## 🚀 Steps

### Step 1: Create S3 Bucket

* Enable **static website hosting**
* Upload `index.html`

---

### Step 2: Create CloudFront Distribution

* Origin: S3 bucket
* Viewer protocol: Redirect HTTP → HTTPS

---

### Step 3: Access Website

```id="f9r2mj"
https://<cloudfront-domain>
```

---

## ✅ Expected Outcome

* Website loads faster globally
* Content cached

---

## 🔐 Learning

👉 Most companies use this for frontend hosting

---

