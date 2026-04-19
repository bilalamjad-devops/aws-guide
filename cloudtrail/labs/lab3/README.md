

## 🔬 Lab 3: Monitor AWS Console Login Activity

📁 `cloudtrail/labs/lab3-monitor-console-logins/README.md`

### 🎯 Objective

Track successful and failed console login attempts.

### 🌍 Industry Use Case

SOC teams monitor login behavior to detect unauthorized access.

### 🏗️ Architecture

CloudTrail → CloudWatch Logs → SNS

### 🚀 Steps

1. Send CloudTrail logs to CloudWatch.
2. Create a metric filter:

   ```
   { $.eventName = ConsoleLogin }
   ```
3. For failed logins:

   ```
   { $.eventName = ConsoleLogin && $.errorMessage = "Failed authentication" }
   ```
4. Create an alarm and configure SNS notifications.

### 🧪 Testing

Attempt a login with incorrect credentials.

### ✅ Expected Outcome

An alert is sent when a login attempt occurs.

---

## Lab 3 in Simple


# 🔬 Lab 3 (Simple): Monitor Login Activity

### 🧠 What is the idea?

Track:

* Who logged in
* Who failed login

👉 Very important for security (hack attempts)

---

## 🧩 Flow

CloudTrail → CloudWatch → SNS

---

## 🪜 Steps

### Step 1: Logs already going to CloudWatch

(from Lab 2 setup)

---

### Step 2: Create filter for login

#### All logins:

```
{ $.eventName = ConsoleLogin }
```

#### Failed logins:

```
{ $.eventName = ConsoleLogin && $.errorMessage = "Failed authentication" }
```

👉 Meaning:

* Detect login attempts
* Detect failed password attempts

---

### Step 3: Create Alarm

* Same as before
* Connect SNS email

---

### Step 4: Test

👉 Try:

* Wrong password login

---

## ✅ Result

You get alert like:

> “Failed login attempt detected”

---

## 🧠 Real-world meaning

> “Someone is trying to hack or access account”

---
