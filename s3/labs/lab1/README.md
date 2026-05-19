


## Question 1

You asked:

> Can we work with only one option?
>
> * open public access
> * add public bucket policy

Answer:

No. Usually both are needed for direct public S3 website hosting.

Because they do different jobs.

Think like this:

| Feature             | Purpose            |
| ------------------- | ------------------ |
| Block Public Access | Global safety lock |
| Bucket Policy       | Actual permission  |

Example:

```text id="y2nl3m"
Block Public Access = OFF
```

means:

> “I allow this bucket to potentially become public.”

But this alone does NOT give public read permission.

Then:

```text id="q4a7s6"
Bucket Policy
```

means:

> “Allow everyone to read objects.”

Without policy:

* access denied

Without disabling block public access:

* AWS ignores your public policy

So for direct S3 website hosting:

```text id="ml4j72"
1. Disable Block Public Access
2. Add Public Read Bucket Policy
```

Both are required.

---

## Question 2

You said:

> I enabled static hosting + CloudFront
> and DID NOT add bucket policy

Very important concept:

There are TWO ways CloudFront can connect to S3.

---

<details>
  <summary> <H3>Method 1 — S3 Website Endpoint (Old/Simpler) </H3></summary>
  

Architecture:

```text id="u6i3nr"
Users
  ↓
CloudFront
  ↓
Public S3 Website Endpoint
```

In this method:

* S3 bucket MUST be public
* public bucket policy required

Because CloudFront accesses public website endpoint.
  
  
</details>


---

<details>
  <summary>  <h3>Method 2 — Private S3 Bucket + OAC/OAI (Recommended)</h3></summary>
  
  
  



Architecture:

```text id="7k4d9m"
Users
  ↓
CloudFront
  ↓
Private S3 Bucket
```

Here:

* users never access S3 directly
* only CloudFront can access bucket

This is modern best practice.

In this setup:

* S3 bucket remains private
* Block Public Access stays ON
* CloudFront gets special permission

This is likely what happened in your lab.

AWS automatically may have created:

* OAC (Origin Access Control)
  or older:
* OAI (Origin Access Identity)

So you did not need public bucket policy.

---
  
</details>


---

# VERY Important Beginner Understanding

There are TWO different S3 URLs:

## 1. Static Website Endpoint

Example:

```text id="h6d7if"
bucket.s3-website-us-east-1.amazonaws.com
```

Features:

* supports index.html
* supports error pages
* requires public access

---

## 2. S3 REST Endpoint

Example:

```text id="z9z0ee"
bucket.s3.amazonaws.com
```

Features:

* private access possible
* used with CloudFront OAC/OAI
* recommended for production

---

# Modern Production Best Practice

Today professionals usually do:

```text id="by6kcl"
Private S3 Bucket
        ↓
CloudFront OAC
        ↓
HTTPS Website
```

NOT:

```text id="x1mb7m"
Public S3 Bucket
        ↓
CloudFront
```

Because private bucket is more secure.

---

# For Your Portfolio

I recommend:

## First Project (Learning)

Use:

* public S3
* static website hosting
* bucket policy

because easier to understand.

---

## Second Version (Professional)

Use:

* private S3
* CloudFront OAC
* no public bucket access

Then in interview you can explain:

> “Initially I used public static hosting to understand S3 website hosting. Then I improved security using private S3 with CloudFront OAC.”

That sounds very strong.



---

# 🧪 Lab 1: Static Website Hosting (Industry Standard)

📁 `s3/labs/lab1-static-website/README.md`

## 🎯 Objective

Host a static website using S3.

---

## 🏗️ Architecture

```id="k1n7xp"
User → S3 (static website)
```

---

## 🚀 Steps

### Step 1: Create Bucket

* Name: `my-static-site`
* Disable block public access (only for this lab)

---

### Step 2: Upload Files

Upload:

* `index.html`
* CSS / JS files

---

### Step 3: Enable Static Hosting

* Enable static website hosting
* Set index document → `index.html`

---

### Step 4: Add Bucket Policy

Allow public read:

```json id="z8m3qa"
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::my-static-site/*"
    }
  ]
}
```

---

## ✅ Expected Outcome

* Website accessible via S3 URL

---

## 🔐 Learning

👉 Real production uses **CloudFront + S3**, not direct S3

---

