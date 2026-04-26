Perfect — **VPC is the foundation of everything in AWS**.
If this is weak → everything is weak.
If this is strong → you look like a real engineer.

I’ll keep it **clear, practical, and interview-level strong**.

---

# 📘 `vpc/README.md`

# Amazon VPC (Virtual Private Cloud)

Amazon VPC allows you to create your own private network inside AWS.

👉 Simple idea:

* You control network
* You decide:

  * IP ranges
  * subnets
  * routing
  * security

---

## 🔹 What actually matters

Without VPC:

```id="v1k9pw"
Everything public (insecure ❌)
```

With VPC:

```id="x7m2qa"
Controlled network (secure + structured ✅)
```

---

## 🔹 Core Components (VERY IMPORTANT)

### 1. VPC

* Main network
* Example: `10.0.0.0/16`

---

### 2. Subnets

* **Public Subnet**

  * Has internet access
  * Used for:

    * Load Balancer
    * Bastion host

* **Private Subnet**

  * No direct internet
  * Used for:

    * EC2 (backend)
    * RDS

---

### 3. Internet Gateway (IGW)

* Allows internet access for public subnet

---

### 4. NAT Gateway

* Allows private subnet → internet (outbound only)

👉 Example:

* Private EC2 can install packages

---

### 5. Route Tables

* Control traffic flow

---

### 6. Security Groups

* Firewall for instances

---

## 🔹 Real-world Architecture

```id="k3x9pt"
VPC
├── Public Subnet
│     └── Load Balancer
│
└── Private Subnet
      ├── Backend (EC2 / EKS)
      └── RDS
```

---

## 🔹 DevOps Perspective (IMPORTANT)

👉 In real systems:

* ALB → Public subnet
* App → Private subnet
* DB → Private subnet

👉 No direct internet access to backend/database

---

## 🔹 Security Best Practices

* Use private subnets for sensitive services
* Restrict access via security groups
* Use NAT instead of public IP
* Use NACLs (optional advanced)
* Avoid exposing databases publicly

---

## 🔹 Common Use Cases

* Secure application hosting
* Multi-tier architecture
* Kubernetes clusters (EKS)
* Database isolation

---

Commit Date: 26-April-2026
