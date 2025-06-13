# Day-1 AWS-Class Task  
# 🛠️ AWS EC2 Web Server Setup with Custom VPC

This project walks through setting up an EC2 instance inside a custom VPC on AWS, including all necessary networking components. The EC2 instance runs a basic web server and is accessible over the internet.

---

## ✅ Steps

### 1. Creating Key Pair  
![Step 1 - Key Pair](https://github.com/user-attachments/assets/c5cd4860-dc35-42fa-8949-3084777b1ddb)

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

| Component       | Description                                           |
|----------------|-------------------------------------------------------|
| **Route Table** | Routes internet traffic to the IGW for public subnet |
| **Security Group** | Allows SSH (22) and HTTP (80) access              |

![Step 5 - Route Table](https://github.com/mayurminfy1/AWS-assignment/blob/main/route-table.png?raw=true)

---

### 6. Launching EC2 Instance  
![Step 6 - Launch EC2](https://github.com/mayurminfy1/AWS-assignment/blob/main/ec2-instance.png?raw=true)

---

### 7. Testing the Web Server  
Visit the public IPv4 address of your EC2 instance in a browser.

![Step 7 - Web Server Test](https://github.com/mayurminfy1/AWS-assignment/blob/main/result.png?raw=true)

---

## 🧹 Cleanup

To avoid incurring costs on your AWS account, follow these cleanup steps:

| Step | Action |
|------|--------|
| 1️⃣  | Terminate EC2 Instance → EC2 → Instances → Terminate |
| 2️⃣  | Delete Key Pair → EC2 → Key Pairs → Delete |
| 3️⃣  | Delete Security Group → EC2 → Security Groups → Delete |
| 4️⃣  | Detach & Delete Internet Gateway → VPC → Internet Gateways |
| 5️⃣  | Delete Route Table → VPC → Route Tables |
| 6️⃣  | Delete Subnet → VPC → Subnets |
| 7️⃣  | Delete VPC → VPC → Your VPCs |

![Step 8 - Cleanup](https://github.com/mayurminfy1/AWS-assignment/blob/main/cleanup.png?raw=true)

---

# 🧪 Take-Home Assignment - Day 1 DevOps AWS

## 🏗️ Project: Build a Two-Tier Web Application Infrastructure

This assignment focuses on designing a secure AWS infrastructure with a public-facing web server and a private database server.  
The goal is to build networking, compute, and security layers using core AWS services.

---


---

## 🧱 Step-by-Step Execution with Screenshots

| Step | Component                | CIDR / Details             | Purpose/Description                                                                 |
|------|--------------------------|----------------------------|--------------------------------------------------------------------------------------|
| 1️⃣  | **VPC: `two-tier-vpc`**  | `10.10.0.0/16`             | Custom VPC to isolate and manage networking for the app                             |
| 2️⃣  | **Public Subnet**        | `10.10.1.0/24`             | Hosts public-facing resources like the Web Server                                   |
| 3️⃣  | **Private Subnet**       | `10.10.2.0/24`             | Hosts private resources like the DB Server, no direct internet access               |
| 4️⃣  | **Internet Gateway**     | Attached to VPC            | Enables public subnet internet access                                               |
| 5️⃣  | **Route Tables**         | Updated for public subnet  | Routes traffic from public subnet to Internet Gateway                               |
| 6️⃣  | **Security Group: `webapp-sg`** | HTTP (80), SSH (22) | Allows web and secure shell access                                                  |
| 7️⃣  | **Security Group: `database-sg`** | MySQL (3306) from webapp-sg | Only allows DB access from the web server                                           |
| 8️⃣  | **EC2 Instances**        | Web in public, DB in private | Web server is accessible, DB is protected                                           |
| 9️⃣  | **SSH Access Test**      | Web Server                 | Confirmed working SSH connection using key and public IP                            |
| 🔟  | **Web Server Test**      | Browser                    | Successfully hosted HTTP page is visible                                            |

---

### 🔐 Security Group: `database-sg`

![Database SG Rules](https://github.com/mayurminfy1/Day1-aws-console/blob/main/day-1-takehome/ss3.png?raw=true)

---

### 🖥️ EC2 Instances Created

![EC2 Instances List](https://github.com/mayurminfy1/Day1-aws-console/blob/main/day-1-takehome/ss1.png?raw=true)

---

### 🧑‍💻 SSH Access to Web Server

![SSH Access](https://github.com/mayurminfy1/Day1-aws-console/blob/main/day-1-takehome/ss4.png?raw=true)

---

### 📶 Ping Test (Web Server)

![Ping DB](https://github.com/mayurminfy1/Day1-aws-console/blob/main/day-1-takehome/ss5.png?raw=true)

---

### 🌐 Web Server Running

![Web Server Running](https://github.com/mayurminfy1/Day1-aws-console/blob/main/day-1-takehome/ss6.png?raw=true)

---

## 🌍 Web Server Public IP

> http://13.235.0.245
