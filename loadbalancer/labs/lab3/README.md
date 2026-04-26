---

# 🧪 Lab 3: ALB with Auto Scaling (Real Industry)

📁 `load-balancer/labs/lab3-alb-asg/README.md`

## 🎯 Objective

Automatically scale servers behind Load Balancer.

---

## 🏗️ Architecture

```id="kw0k3n"
User → ALB → Auto Scaling Group → EC2 instances
```

---

## 🚀 Steps

### Step 1: Create Launch Template

* Install web server in user-data

---

### Step 2: Create Auto Scaling Group

* Attach to target group
* Min: 2
* Max: 4

---

### Step 3: Add Scaling Policy

Example:

* CPU > 70% → add instance
* CPU < 30% → remove instance

---

## ✅ Expected Outcome

* Traffic increases → new EC2 created
* Traffic decreases → instances removed

---

## 🔐 Learning

👉 This is REAL production setup
👉 Used in almost every scalable system

---

# 🎯 Final Understanding

Load Balancer is used with:

* EC2 → classic apps
* ECS / EKS → containers
* Auto Scaling → scalability



Commit Date: 26-April-2026
