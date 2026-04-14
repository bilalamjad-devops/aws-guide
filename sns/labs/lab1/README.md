

## 🧪 Lab 1: Create an SNS Topic and Send an Email Notification

📁 `sns/labs/lab1-create-sns-topic/README.md`

# Lab 1: Create an Amazon SNS Topic and Send Notifications

## 🎯 Objective

Learn how to create an SNS topic, subscribe via email, and publish a message.

## 📋 Prerequisites

* AWS account
* IAM user with SNS permissions
* Verified email address

## 🏗️ Architecture

```
SNS Topic → Email Subscriber
```

## 🚀 Steps

### Step 1: Create an SNS Topic

1. Sign in to the AWS Management Console.
2. Navigate to **Amazon SNS**.
3. Click **Topics → Create topic**.
4. Select **Standard**.
5. Enter the name: `MyFirstSNSTopic`.
6. Click **Create topic**.

### Step 2: Create a Subscription

1. Open the newly created topic.
2. Click **Create subscription**.
3. Choose protocol: **Email**.
4. Enter your email address.
5. Click **Create subscription**.
6. Confirm the subscription from your inbox.

### Step 3: Publish a Message

1. Open the SNS topic.
2. Click **Publish message**.
3. Enter:

   * Subject: `Test Notification`
   * Message: `Hello! This is a test message from Amazon SNS.`
4. Click **Publish**.

## ✅ Expected Outcome

You will receive an email notification from Amazon SNS.

## 🔐 Security Best Practices

* Enable server-side encryption.
* Restrict access using IAM policies.
* Monitor activity using AWS CloudTrail.

## 🧹 Cleanup

* Delete the SNS topic.
* Remove the email subscription.

---

Commit Date: 15-April-2026
