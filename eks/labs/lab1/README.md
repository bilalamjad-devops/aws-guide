
---

# 🧪 Lab 1: Deploy App on EKS (Basic)

📁 `eks/labs/lab1-basic-deploy/README.md`

## 🎯 Objective

Deploy a simple application to EKS cluster.

---

## 🏗️ Architecture

```id="l9x3bc"
EKS → Deployment → Pods
```

---

## 🚀 Steps

### Step 1: Create Deployment

```yaml id="m2v7re"
apiVersion: apps/v1
kind: Deployment
metadata:
  name: my-app
spec:
  replicas: 2
  selector:
    matchLabels:
      app: my-app
  template:
    metadata:
      labels:
        app: my-app
    spec:
      containers:
      - name: my-app
        image: nginx
        ports:
        - containerPort: 80
```

---

### Step 2: Apply

```bash id="p3z8ks"
kubectl apply -f deployment.yaml
```

---

### Step 3: Verify

```bash id="b7f4qa"
kubectl get pods
```

---

## ✅ Expected Outcome

* Pods are running
* Application deployed inside cluster

---

## 🔐 Learning

👉 Kubernetes manages containers automatically

---


