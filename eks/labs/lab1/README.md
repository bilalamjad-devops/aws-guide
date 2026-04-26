
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

# 🧪 Lab 2: Expose App using Service + Load Balancer

📁 `eks/labs/lab2-service-lb/README.md`

## 🎯 Objective

Expose application to internet.

---

## 🏗️ Architecture

```id="r8n2yt"
User → LoadBalancer Service → Pods
```

---

## 🚀 Steps

### Step 1: Create Service

```yaml id="w1k9dp"
apiVersion: v1
kind: Service
metadata:
  name: my-app-service
spec:
  type: LoadBalancer
  selector:
    app: my-app
  ports:
    - port: 80
      targetPort: 80
```

---

### Step 2: Apply

```bash id="h5j6mq"
kubectl apply -f service.yaml
```

---

### Step 3: Get External IP

```bash id="c4z2lx"
kubectl get svc
```

---

## ✅ Expected Outcome

* AWS creates Load Balancer
* You get public IP / DNS
* App accessible from browser

---

## 🔐 Learning

👉 Kubernetes integrates with AWS Load Balancer automatically

---

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

