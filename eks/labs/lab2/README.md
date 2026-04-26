

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
