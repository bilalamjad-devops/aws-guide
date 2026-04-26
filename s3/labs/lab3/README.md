

# 🧪 Lab 3: CI/CD Artifact Storage

📁 `s3/labs/lab3-artifacts/README.md`

## 🎯 Objective

Store build artifacts from pipeline.

---

## 🏗️ Architecture

```id="d7k4xp"
Jenkins → S3 → Artifact Storage
```

---

## 🚀 Steps

### Step 1: Create Bucket

* Name: `my-artifacts-bucket`

---

### Step 2: Upload Artifact (example)

```bash id="q2w8lz"
aws s3 cp app.zip s3://my-artifacts-bucket/
```

---

### Step 3: Download Artifact

```bash id="v5n3ka"
aws s3 cp s3://my-artifacts-bucket/app.zip .
```

---

## ✅ Expected Outcome

* Artifacts stored and retrieved

---

## 🔐 Learning

👉 Used in:

* Jenkins pipelines
* Backup systems
* Deployment workflows

---
