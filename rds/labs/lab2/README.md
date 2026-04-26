# 🧪 Lab 2: RDS with Application (Real DevOps)

📁 `rds/labs/lab2-rds-with-app/README.md`

## 🎯 Objective

Connect your backend application to RDS.

---

## 🏗️ Architecture

```id="27drp9"
Frontend → Backend (Node.js) → RDS
```

---

## 🚀 Steps

### Step 1: Update Backend `.env`

```id="3w9smb"
DB_HOST=<rds-endpoint>
DB_USER=admin
DB_PASSWORD=StrongPassword123
DB_NAME=mydb
```

---

### Step 2: Update DB Connection Code

Example (Node.js):

```js
const mysql = require("mysql2");

const connection = mysql.createConnection({
  host: process.env.DB_HOST,
  user: process.env.DB_USER,
  password: process.env.DB_PASSWORD,
  database: process.env.DB_NAME,
});
```

---

### Step 3: Run Application

```bash id="6g3h5k"
npm start
```

---

## ✅ Expected Outcome

* Application stores data in RDS
* Data persists even if app restarts

---

## 🔐 Real-world Tip

👉 Never hardcode DB credentials
👉 Use:

* AWS Secrets Manager
* Kubernetes Secrets

---
