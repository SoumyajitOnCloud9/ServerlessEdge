# 🚀 Serverless Employee Management System (AWS)

A **production-ready serverless web application** built on AWS that allows users to **store employee data** and **view all employees** using a scalable, cost-efficient architecture.

![AWS](https://img.shields.io/badge/AWS-Cloud-orange?logo=amazonaws)
![AWS Lambda](https://img.shields.io/badge/AWS-Lambda-yellow?logo=awslambda)
![API Gateway](https://img.shields.io/badge/AWS-API%20Gateway-blue?logo=amazonaws)
![DynamoDB](https://img.shields.io/badge/AWS-DynamoDB-blue?logo=amazondynamodb)
![S3](https://img.shields.io/badge/AWS-S3-green?logo=amazons3)
![CloudFront](https://img.shields.io/badge/AWS-CloudFront-lightgrey?logo=amazonaws)
![IAM](https://img.shields.io/badge/AWS-IAM-red?logo=amazonaws)


---

## 📌 Project Highlights

- Fully **serverless architecture**
- Scales automatically with demand
- No server or infrastructure management
- Secure IAM-based access
- Low latency using CloudFront
- REST API powered by API Gateway & Lambda

---

## 🖥️ Frontend Preview

![Frontend UI](Front-end%20preview.png)

---

## 🏗️ Architecture Diagram

![Serverless Architecture](Aarchitecture.png)

---

## 🧠 Architecture Overview

**Request Flow:**
Client → CloudFront → S3 → API Gateway → Lambda → DynamoDB

---

### 🔧 AWS Services Used

- 🪣 **Amazon S3** – Static website hosting (HTML, CSS, JavaScript)
- 🌍 **Amazon CloudFront** – Global CDN for low-latency access
- 🔌 **Amazon API Gateway** – REST APIs (POST & GET)
- ⚡ **AWS Lambda** – Business logic execution
- 🗄️ **Amazon DynamoDB** – NoSQL data storage
- 🔐 **AWS IAM** – Secure permission management

---

## 📂 DynamoDB Configuration

| Property | Value |
|--------|------|
| Table Name | `employeeData` |
| Partition Key | `employeeId` |

---

## 🔗 API Design (Production Ready)

### ➕ POST /employee
- **Purpose:** Save employee data
- **Lambda:** `insertEmployeeData`
- **Flow:**
  - User submits form
  - API Gateway triggers POST
  - Lambda validates input
  - Data stored in DynamoDB

### 📥 GET /employees
- **Purpose:** Fetch all employees
- **Lambda:** `getEmployees`
- **Flow:**
  - User clicks *View All Employees*
  - API Gateway triggers GET
  - Lambda fetches data from DynamoDB
  - Response returned to UI

---

## 🧑‍💻 Website Functionality

### 🔴 Save Employee Data
- Executes **POST API**
- Calls `insertEmployeeData` Lambda
- Stores record in DynamoDB

### 🔵 View All Employees
- Executes **GET API**
- Calls `getEmployees` Lambda
- Fetches and displays data

---

## ⚙️ Project Setup Steps

### 1️⃣ Create DynamoDB Table
- Table name: `employeeData`
- Primary key: `employeeId`

---

### 2️⃣ Create IAM Role
- **Trusted Entity:** AWS Lambda
- **Permissions:** DynamoDB (Read/Write)
- Follow **least-privilege principle**

---

### 3️⃣ Create Lambda Functions
- `insertEmployeeData`
- `getEmployees`
- Attach IAM role
- Enable structured logging (CloudWatch)

---

### 4️⃣ Configure API Gateway
- REST API (Edge-Optimized)
- Create methods:
  - `POST` → `insertEmployeeData`
  - `GET` → `getEmployees`
- Enable **CORS**
- Deploy API
- Copy **Invoke URL**

---

### 5️⃣ Frontend Deployment (S3)
- Upload HTML, CSS, JavaScript
- Configure API URL in JavaScript
- Enable static website hosting

---

### 6️⃣ CloudFront Integration (Recommended)
✅ **Production Best Practice**

- Use CloudFront in front of S3
- Keep S3 bucket **private**
- Serve content securely via CloudFront
- Improves performance and security

> ⚠️ If CloudFront is not used, S3 bucket must be public (not recommended for production)

---

## 🔐 Security Best Practices

- IAM roles with least privilege
- No hardcoded credentials
- Private S3 bucket with CloudFront
- CORS restricted to frontend domain
- Serverless isolation per service

---

## 📈 Production Benefits

- Auto-scaling with AWS Lambda
- High availability
- Pay-per-use pricing
- Zero server maintenance
- Easily extensible for CRUD operations

---

## 🧑‍💻 Author

**Soumyajit Saha**  
*Aspiring AWS & DevOps Engineer*  
🔗 [LinkedIn](https://www.linkedin.com/in/soumyajit-saha-5a8932282/) | [GitHub](https://github.com/SoumyajitOnCloud9/VPC-Bridge/tree/main)

---
## 📄 License

This project is intended for **learning, demonstration, and portfolio use**.
Feel free to fork and adapt for your own AWS DevOps learning path.  

---


🌟 **Like what you see?** Give this repo a star and share it with fellow cloud enthusiasts!  
☁️ **More AWS projects are on the way — stay connected!**


