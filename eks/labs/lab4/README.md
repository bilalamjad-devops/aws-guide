

# 🧪 Lab 4 (Advanced): Auto Scaling (HPA)

📁 `eks/labs/lab4-hpa/README.md`

## 🎯 Objective

Automatically scale pods based on load.

---

## 🏗️ Architecture

```id="t6m1vw"
High Traffic → HPA → More Pods
```

---

## 🚀 Steps

### Step 1: Enable metrics server

```bash id="o2x7qa"
kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml
```

---

### Step 2: Create HPA

```bash id="z9w3lk"
kubectl autoscale deployment my-app --cpu-percent=50 --min=2 --max=5
```

---

### Step 3: Verify

```bash id="q4b6yr"
kubectl get hpa
```

---

## ✅ Expected Outcome

* Load increases → pods increase
* Load decreases → pods decrease

---

## 🔐 Learning

👉 This is real scalability in production

---

# 🎯 Final Understanding

EKS completes your full DevOps flow:

```id="d3x8vm"
Code → Jenkins → Docker → ECR → EKS → Load Balancer → Users
```

---

👉 If you understand this:

* You are no longer beginner
* You are entering **real DevOps engineer level**

---
