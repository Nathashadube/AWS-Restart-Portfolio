# AWS EC2 Instance Launch – Lab Report

## Overview
This lab demonstrates the process of launching an **Amazon EC2 instance** on AWS using the EC2 Management Console. The steps include selecting an Amazon Machine Image (AMI), instance type, key pair, network configuration, storage options, and additional instance settings. The instance was successfully created and initiated.

---

## 1. Instance Details

- **Instance Name:** Web Server  
- **Region:** United States (Oregon)  
- **Instance ID:** i-0c7497028809812ef  
- **Status:** Successfully launched  
- **AMI (Amazon Machine Image):** Amazon Linux 2023 AMI (Free tier eligible)  
- **Instance Type:** t2.micro (1 vCPU, 1 GiB memory)  
- **Architecture:** 64-bit (x86)  

---

## 2. Key Configuration Information

### **Key Pair (Login)**
- A new or existing key pair was selected for SSH access to the EC2 instance.
- The private key file (`.pem`) is required for secure connection to the instance.

### **Network Settings**
- **VPC:** Default VPC (preconfigured by AWS)  
- **Subnet:** Automatically assigned (auto-assign public IP enabled)  
- **Security Group:** A new security group was created with rules that allow:
  - **Inbound traffic:** SSH, HTTP, and HTTPS  
  - **Outbound traffic:** All traffic (default)

---

## 3. Storage Configuration

- **Root Volume Size:** 8 GB (default configuration)  
- **Volume Type:** General Purpose SSD (gp3)  
- **Encryption:** Not encrypted (default)  

---

## 4. Advanced Details

- **Shutdown Behavior:** Stop (to preserve data when stopped)  
- **Monitoring:** Default (detailed monitoring available as an optional feature)  
- **User Data:** Startup script provided for web server installation and configuration

### **User Data Script (Example)**
```bash
#!/bin/bash
yum update -y
yum install -y httpd
systemctl start httpd
systemctl enable httpd
echo "<h1>Welcome to Your Web Server</h1>" > /var/www/html/index.html
