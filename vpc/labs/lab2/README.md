

# 🧪 Lab 2: NAT Gateway (Private Internet Access)

📁 `vpc/labs/lab2-nat-gateway/README.md`

## 🎯 Objective

Allow private subnet to access internet securely.

---

## 🏗️ Architecture

```id="q9x2lm"
Private EC2 → NAT → Internet
```

---

## 🚀 Steps

### Step 1: Create NAT Gateway

* Place in public subnet
* Attach Elastic IP

---

### Step 2: Update Route Table (Private)

```id="c6v1kp"
0.0.0.0/0 → NAT Gateway
```

---

### Step 3: Test

SSH into private EC2 (via bastion or public EC2)

```bash id="f2m8rt"
sudo apt update
```

---

## ✅ Expected Outcome

* Private EC2 can access internet
* But no inbound access

---

## 🔐 Learning

👉 This is real production setup

---
