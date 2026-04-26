

# 🧪 Lab 1: Static Website Hosting (Industry Standard)

📁 `s3/labs/lab1-static-website/README.md`

## 🎯 Objective

Host a static website using S3.

---

## 🏗️ Architecture

```id="k1n7xp"
User → S3 (static website)
```

---

## 🚀 Steps

### Step 1: Create Bucket

* Name: `my-static-site`
* Disable block public access (only for this lab)

---

### Step 2: Upload Files

Upload:

* `index.html`
* CSS / JS files

---

### Step 3: Enable Static Hosting

* Enable static website hosting
* Set index document → `index.html`

---

### Step 4: Add Bucket Policy

Allow public read:

```json id="z8m3qa"
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::my-static-site/*"
    }
  ]
}
```

---

## ✅ Expected Outcome

* Website accessible via S3 URL

---

## 🔐 Learning

👉 Real production uses **CloudFront + S3**, not direct S3

---

