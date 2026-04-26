
# 🧪 Lab 1: ALB with Multiple EC2 (High Availability)

📁 `load-balancer/labs/lab1-alb-ec2/README.md`

## 🎯 Objective

Distribute traffic across multiple EC2 instances using ALB.

---

## 🏗️ Architecture

```id="z92t3h"
User → ALB → EC2-1
           → EC2-2
```

---

## 🚀 Steps

### Step 1: Launch 2 EC2 instances

Install simple web server:

```bash
sudo apt update
sudo apt install apache2 -y
echo "Server 1" | sudo tee /var/www/html/index.html
```

(On second instance → change text to "Server 2")

---

### Step 2: Create Target Group

* Type: Instance
* Protocol: HTTP
* Port: 80
* Add both EC2 instances

---

### Step 3: Create Application Load Balancer

* Scheme: Internet-facing
* Listener: HTTP (80)
* Attach target group

---

### Step 4: Access ALB DNS

Open:

```
http://<alb-dns>
```

---

## ✅ Expected Outcome

* Refresh page → traffic switches between servers
* If one server stops → still works

---

## 🔐 Learning

👉 Load Balancer ensures high availability
👉 No direct dependency on single server

---

Commit Date: 26-April-2026
