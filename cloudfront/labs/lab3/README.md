
# 🧪 Lab 3: Secure Content (Signed URL)

📁 `cloudfront/labs/lab3-signed-url/README.md`

## 🎯 Objective

Restrict access to private content.

---

## 🏗️ Architecture

```id="u3k9xp"
User → Signed URL → CloudFront → Private S3
```

---

## 🚀 Steps

### Step 1: Make S3 Private

* Disable public access

---

### Step 2: Create CloudFront

* Use Origin Access Control (OAC)

---

### Step 3: Generate Signed URL

(Example concept)

* Only authorized users can access content

---

## ✅ Expected Outcome

* Unauthorized users cannot access files

---

## 🔐 Learning

👉 Used in:

* paid content
* private downloads
* secure media

---

# 🎯 Final Understanding

CloudFront sits at top layer:

```id="t5v1qn"
User → CloudFront → Backend (S3 / ALB / EKS)
```

---

👉 It gives:

* speed
* security
* scalability

---


