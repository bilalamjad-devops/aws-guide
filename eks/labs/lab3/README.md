

# 🧪 Lab 3: Rolling Update (Zero Downtime)

📁 `eks/labs/lab3-rolling-update/README.md`

## 🎯 Objective

Update application without downtime.

---

## 🏗️ Architecture

```id="v2q7ne"
Old Pods → Gradual Replacement → New Pods
```

---

## 🚀 Steps

### Step 1: Update Image

```bash id="y5k8rt"
kubectl set image deployment/my-app my-app=nginx:latest
```

---

### Step 2: Watch rollout

```bash id="g8h3sx"
kubectl rollout status deployment/my-app
```

---

## ✅ Expected Outcome

* Pods updated one by one
* No downtime

---

## 🔐 Learning

👉 This is used in production deployments

---
