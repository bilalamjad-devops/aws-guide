
# 🧪 Lab 3: ECR with EKS (Production Deployment)

📁 `ecr/labs/lab3-ecr-eks/README.md`

## 🎯 Objective

Deploy application from ECR to Kubernetes (EKS).

---

## 🏗️ Architecture

```id="m1x8cd"
ECR → EKS → Pods
```

---

## 🚀 Steps

### Step 1: Update Kubernetes Deployment

```yaml
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
        image: <account-id>.dkr.ecr.ap-south-1.amazonaws.com/my-app:latest
        ports:
        - containerPort: 3000
```

---

### Step 2: Apply Deployment

```bash
kubectl apply -f deployment.yaml
```

---

### Step 3: Verify

```bash
kubectl get pods
```

---

## ✅ Expected Outcome

* Pods running using ECR image

---

## 🔐 Important Note

👉 EKS must have permission to pull from ECR
(Usually via IAM role)

---

# 🎯 Final Understanding

ECR sits in middle of:

```id="k2x8vn"
CI (Jenkins) → ECR → CD (EKS)
```

---

👉 If you understand ECR:

* You understand CI/CD pipeline flow
* You can replace DockerHub with production-grade setup



Commit Date: 26-April-2026
