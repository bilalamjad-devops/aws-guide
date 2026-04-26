
# 🧪 Lab 2: Jenkins → ECR (Real CI Pipeline)

📁 `ecr/labs/lab2-jenkins-ecr/README.md`

## 🎯 Objective

Push Docker image to ECR using Jenkins pipeline.

---

## 🏗️ Architecture

```id="z4p9rx"
GitHub → Jenkins → ECR
```

---

## 🚀 Steps

### Step 1: Attach IAM Role to Jenkins EC2

Permissions:

* `AmazonEC2ContainerRegistryFullAccess`

---

### Step 2: Install AWS CLI on Jenkins

```bash
sudo apt install awscli -y
```

---

### Step 3: Jenkins Pipeline

```bash
pipeline {
    agent any

    stages {
        stage('Build Image') {
            steps {
                sh 'docker build -t my-app .'
            }
        }

        stage('Login to ECR') {
            steps {
                sh '''
                aws ecr get-login-password --region ap-south-1 | \
                docker login --username AWS --password-stdin <account-id>.dkr.ecr.ap-south-1.amazonaws.com
                '''
            }
        }

        stage('Tag Image') {
            steps {
                sh 'docker tag my-app:latest <account-id>.dkr.ecr.ap-south-1.amazonaws.com/my-app:latest'
            }
        }

        stage('Push Image') {
            steps {
                sh 'docker push <account-id>.dkr.ecr.ap-south-1.amazonaws.com/my-app:latest'
            }
        }
    }
}
```

---

## ✅ Expected Outcome

* Jenkins builds and pushes image automatically

---

## 🔐 Learning

👉 This is REAL CI pipeline used in companies

---


Commit Date: 26-April-2026
