

# 🔬 Lab 2: Scan Docker Images (ECR)

📁 `lab2-ecr-image-scanning/README.md`

## 🎯 Objective

Scan container images for vulnerabilities before deployment.

---

## 🌍 Real-World Scenario

Before deploying Docker images:

> “Check if image contains vulnerable software”

---

## 🪜 Steps

### Step 1: Push Image to ECR

* Create ECR repo
* Push Docker image

---

### Step 2: Enable scanning

* Go to Inspector
* Enable **ECR scanning**

---

### Step 3: View findings

* Go to Findings
* Filter: ECR

---

## ✅ Result

You will see:

* Vulnerable libraries
* CVEs inside image

---

## 🧠 Real Meaning

> “Your Docker image may be insecure”

---

## 🔐 Best Practice

* Use minimal base images
* Update dependencies

---

---
