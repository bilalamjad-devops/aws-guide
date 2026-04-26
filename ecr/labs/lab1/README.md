
# 🧪 Lab 1: Push Docker Image to ECR

📁 `ecr/labs/lab1-push-image/README.md`

## 🎯 Objective

Build a Docker image and push it to ECR.

---

## 🏗️ Architecture

```id="7n3qkf"
Local / Jenkins → ECR
```

---

## 🚀 Steps

### Step 1: Create ECR Repository

* Go to ECR → Create repository
* Name: `my-app`

---

### Step 2: Authenticate Docker

```bash
aws ecr get-login-password --region ap-south-1 | \
docker login --username AWS --password-stdin <account-id>.dkr.ecr.ap-south-1.amazonaws.com
```

---

### Step 3: Build Image

```bash
docker build -t my-app .
```

---

### Step 4: Tag Image

```bash
docker tag my-app:latest <account-id>.dkr.ecr.ap-south-1.amazonaws.com/my-app:latest
```

---

### Step 5: Push Image

```bash
docker push <account-id>.dkr.ecr.ap-south-1.amazonaws.com/my-app:latest
```

---

## ✅ Expected Outcome

* Image visible in ECR
* Ready for deployment

---

## 🔐 Learning

👉 This replaces DockerHub in production

---


Commit Date: 26-April-2026
