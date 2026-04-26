

# 🧪 Lab 1: Create Basic VPC (Public + Private)

📁 `vpc/labs/lab1-basic-vpc/README.md`

## 🎯 Objective

Create a VPC with public and private subnets.

---

## 🏗️ Architecture

```id="u1n8zx"
VPC
├── Public Subnet → EC2
└── Private Subnet → EC2
```

---

## 🚀 Steps

### Step 1: Create VPC

* CIDR: `10.0.0.0/16`

---

### Step 2: Create Subnets

* Public: `10.0.1.0/24`
* Private: `10.0.2.0/24`

---

### Step 3: Attach Internet Gateway

* Attach to VPC

---

### Step 4: Route Table (Public)

* Add route:

```id="x4k7ab"
0.0.0.0/0 → IGW
```

---

### Step 5: Launch EC2

* Public subnet → accessible
* Private subnet → not accessible

---

## ✅ Expected Outcome

* Public EC2 accessible
* Private EC2 not accessible

---

## 🔐 Learning

👉 Public vs Private concept

---
