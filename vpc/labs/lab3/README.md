

# 🧪 Lab 3: 3-Tier Architecture (Real Industry)

📁 `vpc/labs/lab3-3tier-architecture/README.md`

## 🎯 Objective

Design a real-world architecture.

---

## 🏗️ Architecture

```id="t4z8nm"
Public Subnet
   → Load Balancer

Private Subnet (App)
   → Backend EC2 / EKS

Private Subnet (DB)
   → RDS
```

---

## 🚀 Steps

### Step 1: Create 3 Subnets

* Public
* Private-App
* Private-DB

---

### Step 2: Place Resources

* ALB → Public
* App → Private-App
* DB → Private-DB

---

### Step 3: Configure Security Groups

* ALB → open 80/443
* App → allow from ALB only
* DB → allow from App only

---

## ✅ Expected Outcome

* Secure layered architecture

---

## 🔐 Learning

👉 This is EXACT production architecture

---
