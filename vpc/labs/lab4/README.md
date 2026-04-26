

# 🧪 Lab 4 (Optional): VPC for EKS

📁 `vpc/labs/lab4-eks-network/README.md`

## 🎯 Objective

Prepare VPC for Kubernetes (EKS).

---

## 🚀 Steps

* Create 2 public + 2 private subnets
* Tag subnets for EKS

Example tags:

```id="z5p3rx"
kubernetes.io/cluster/my-cluster = shared
kubernetes.io/role/elb = 1
kubernetes.io/role/internal-elb = 1
```

---

## 🔐 Learning

👉 EKS depends heavily on VPC design

---

# 🎯 Final Understanding

VPC is foundation:

```id="p7x3lm"
Everything runs inside VPC
```

---

👉 If VPC is correct:

* system is secure
* scalable
* production-ready

---

# 🧠 Big Picture (Final)

Now you understand full architecture:

```id="y3n8kt"
User
 ↓
Route53
 ↓
CloudFront
 ↓
Load Balancer
 ↓
VPC
 ↓
EKS / EC2
 ↓
App
 ↓
RDS / S3
```


