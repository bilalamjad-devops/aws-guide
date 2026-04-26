

Perfect — now you’re at the **core of modern DevOps (Kubernetes on AWS)**.
If you understand this properly, you move from *junior → intermediate level*.

I’ll keep it **clear, practical, and industry-focused**.

---

# 📘 `eks/README.md`

# Amazon EKS (Elastic Kubernetes Service)

Amazon EKS is a managed Kubernetes service that allows you to run containerized applications without managing Kubernetes control plane manually.

👉 Simple idea:

* You build Docker image
* Store in ECR
* Deploy on Kubernetes (EKS)

---

## 🔹 What actually matters

Without EKS:

```id="j1a8kd"
Manual servers + Docker (hard to scale ❌)
```

With EKS:

```id="n7p2qx"
Kubernetes → Auto scaling + self-healing + rolling updates ✅
```

---

## 🔹 Why EKS is important

In real DevOps:

* CI/CD builds image
* Image stored in ECR
* EKS runs containers
* Load Balancer exposes app

👉 EKS = **production-grade deployment platform**

---

## 🔹 Key Components (simple)

* **Cluster** → main Kubernetes control plane
* **Node Group** → EC2 instances (workers)
* **Pod** → running container
* **Deployment** → manages pods
* **Service** → exposes app
* **Ingress / ALB** → external access

---

## 🔹 Real-world Architecture

```id="y6v8pt"
User → Load Balancer → EKS → Pods → Container App
```

---

## 🔹 DevOps Flow (IMPORTANT)

```id="f3x9lm"
GitHub → Jenkins → Build Image → Push to ECR → Deploy to EKS
```

👉 This is your **end-to-end pipeline**

---

## 🔹 Features that matter

* Auto scaling (HPA)
* Self-healing (pods restart automatically)
* Rolling updates (zero downtime)
* High availability (multi AZ)

---

## 🔹 Security Best Practices

* Use IAM roles for service accounts (IRSA)
* Store secrets securely (K8s Secrets / AWS Secrets Manager)
* Use private cluster (production)
* Restrict access using RBAC
* Monitor using CloudWatch

---

## 🔹 Common Use Cases

* Microservices architecture
* High traffic applications
* CI/CD deployments
* Scalable backend systems



Commit Date: 26-April-2026
