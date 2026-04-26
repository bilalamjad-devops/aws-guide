
# 🧪 Lab 2: Path-Based Routing (Microservices)

📁 `load-balancer/labs/lab2-path-routing/README.md`

## 🎯 Objective

Route traffic based on URL path.

---

## 🏗️ Architecture

```id="x8m4q2"
User → ALB
      ├── /api → Backend EC2
      └── / → Frontend EC2
```

---

## 🚀 Steps

### Step 1: Create 2 EC2

* EC2-1 → Frontend
* EC2-2 → Backend

---

### Step 2: Create 2 Target Groups

* TG-frontend
* TG-backend

---

### Step 3: Configure ALB Rules

* `/api/*` → Backend target group
* `/` → Frontend target group

---

## ✅ Expected Outcome

* `/` → frontend
* `/api` → backend

---

## 🔐 Learning

👉 This is how microservices routing works
👉 Used in real production systems

