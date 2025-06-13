# Day-1 AWS-Class Task
# 🛠️ AWS EC2 Web Server Setup with Custom VPC

This project walks through setting up an EC2 instance inside a custom VPC on AWS, including all necessary networking components. The EC2 instance runs a basic web server and is accessible over the internet.

---

## ✅ Steps

### 1. Creating Key Pair  
![Step 1 - Key Pair](https://github.com/user-attachments/assets/c5cd4860-dc35-42fa-8949-3084777b1ddb)
)

---

### 2. Creating the VPC  
![Step 2 - VPC](https://github.com/mayurminfy1/AWS-assignment/blob/main/my-vpc.png?raw=true)

---

### 3. Creating Subnets  
![Step 3 - Subnet](https://github.com/mayurminfy1/AWS-assignment/blob/main/public-subnet.png?raw=true)

---

### 4. Creating Internet Gateway  
![Step 4 - IGW](https://github.com/mayurminfy1/AWS-assignment/blob/main/internet-gateway.png?raw=true)

---

### 5. Configuring Public Route Table and Security Group  
- **Route Table:**  
  ![Step 5 - Route Table](https://github.com/mayurminfy1/AWS-assignment/blob/main/route-table.png?raw=true)



---

### 6. Launching EC2 Instance  
![Step 6 - Launch EC2](https://github.com/mayurminfy1/AWS-assignment/blob/main/ec2-instance.png?raw=true)

---

### 7. Testing the Web Server  
Visit the public IPv4 address of your EC2 instance in a browser.  


![Step 7 - Web Server Test](https://github.com/mayurminfy1/AWS-assignment/blob/main/result.png?raw=true)

## 🌐 Web Server Public IP

> http://13.234.122.140

---

## 🧹 Cleanup

To avoid incurring costs on your AWS account, follow these cleanup steps:

1. **Terminate EC2 Instance**
   - Go to EC2 → Instances → Select your instance → Actions → Terminate

2. **Delete Key Pair**
   - EC2 → Key Pairs → Select and delete your key

3. **Delete Security Group**
   - EC2 → Security Groups → Select your custom group → Delete

4. **Detach and Delete Internet Gateway**
   - VPC → Internet Gateways → Detach from VPC → Delete

5. **Delete Route Table**
   - VPC → Route Tables → Select your custom table → Delete

6. **Delete Subnet**
   - VPC → Subnets → Select and delete

7. **Delete VPC**
   - VPC → Your VPCs → Select your custom VPC → Delete
  
     ![Step 8 - Cleanup](https://github.com/mayurminfy1/AWS-assignment/blob/main/cleanup.png?raw=true)



# 🧪 Take-Home Assignment - Day 1 DevOps AWS

## 🏗️ Project: Build a Two-Tier Web Application Infrastructure

This assignment focuses on designing a secure AWS infrastructure with a public-facing web server and a private database server.  
The goal is to build networking, compute, and security layers using core AWS services.

---

## 🚀 Architecture Overview

  I will create:
- A VPC with public and private subnets
- A Web Server in the public subnet
- A DB Server in the private subnet
- Internet Gateway, Route Tables, and Security Groups for connectivity and isolation

---

## 🧱 Step-by-Step Execution with Screenshots

### 1️⃣ Created VPC `two-tier-vpc` (CIDR: 10.10.0.0/16)  
Custom VPC created to isolate the infrastructure and manage subnets.  


---

### 2️⃣ Created Public Subnet `public-subnet-1` (CIDR: 10.10.1.0/24)  
Subnet created for public-facing resources like the web server.  


---

### 3️⃣ Created Private Subnet `private-subnet-1` (CIDR: 10.10.2.0/24)  
Used for private resources like the database, with no public access.  


---

### 4️⃣ Attached Internet Gateway & Configured Route Table  
Internet Gateway enables internet access for public subnet; route table updated.  


---

### 5️⃣ Created Security Group `webapp-sg`  
Allows HTTP (80) from anywhere and SSH (22) from my IP only for secure access.  


---

### 6️⃣ Created Security Group `database-sg`  
Allows MySQL (3306) access only from webapp-sg, fully blocks public access.  
📷 ![Database SG Rules](https://github.com/mayurminfy1/Day1-aws-console/blob/main/day-1-takehome/ss3.png?raw=true)

---

### 7️⃣ Launched EC2 Instances (Web & DB)  
Deployed `Web-Server` in public subnet and `DB-Server` in private subnet.  
📷 ![EC2 Instances List](https://github.com/mayurminfy1/Day1-aws-console/blob/main/day-1-takehome/ss1.png?raw=true)

---

### 8️⃣ Connected via SSH to Web Server  
SSH access to Web Server confirmed using public IP and SSH key.  
📷 ![SSH Access](https://github.com/mayurminfy1/Day1-aws-console/blob/main/day-1-takehome/ss4.png?raw=true)

---

### 9️⃣ Pinged Web Server  
  
📷 ![Ping DB](https://github.com/mayurminfy1/Day1-aws-console/blob/main/day-1-takehome/ss5.png?raw=true)

---

### 🔟 Web Server Running in Browser  
Successfully accessed the HTTP service hosted on the Web Server.  
📷 ![Web Server Running](https://github.com/mayurminfy1/Day1-aws-console/blob/main/day-1-takehome/ss6.png?raw=true)

---

## 🌐 Web Server Public IP

> http://13.235.0.245  






