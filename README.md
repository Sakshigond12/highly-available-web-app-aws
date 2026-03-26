# Highly Available Web Application using Auto Scaling & Application Load Balancer

# 📌 Project Overview
This project demonstrates how to design and deploy a Highly Available Web Application architecture on AWS. The system automatically scales resources based on demand and distributes traffic across multiple servers to prevent downtime.
This architecture ensures fault tolerance, scalability, and eliminates single points of failure.

---

# 🎯 Problem Statement
During peak sales in an e-commerce platform, the application crashes due to traffic spikes.  
The objective is to build an infrastructure that:

- Automatically scales EC2 instances
- Distributes incoming traffic
- Maintains high availability
- Prevents downtime

---

# 🏗 Architecture
![Architecture diagram](https://github.com/Sakshigond12/highly-available-web-app-aws/blob/a141c8c1ab165c0550cb65e706c0f060a2debdaf/img/Architechture%20diagram.png)

---

# 📂 Project Structure

```
highly-available-web-app-aws/

├── README.md
├── index.html
└── img
    ├── alb.png
    |── architecture.png
    ├── target-group.png
    ├── ec2.png
    ├── auto-scaling.png
    └── cloudwatch.png

```

---

# ☁ AWS Services Used

- Amazon EC2
- Application Load Balancer
- Auto Scaling Group
- Amazon CloudWatch
- Amazon VPC
- Internet Gateway
- Public Subnets
- CloudWatch

---

# ⚙ Infrastructure Setup

### 1️⃣ Networking Setup
- Created a Custom VPC
- Created 2 Public Subnets in different Availability Zones
- Attached an Internet Gateway
- Configured Route Tables

---

### 2️⃣ Launch Template
Created a Launch Template with User Data script to install Apache Web Server.

Example User Data Script:
```bash
sudo apt update -y
sudo apt install apache2 -y
sudo systemctl start apache2
sudo systemctl enable apache2
```

---

### 3️⃣ Auto Scaling Group

Configured Auto Scaling with:

Minimum Instances: 2  
Maximum Instances: 5  

Scaling Policy based on CPU Utilization.

---

### 4️⃣ Application Load Balancer

Configured an Application Load Balancer with:

- HTTP Listener
- Target Group
- Health Checks enabled

Traffic is distributed across multiple EC2 instances.

---

## 📊 Monitoring

Application performance is monitored using Amazon CloudWatch.
Metrics Observed:

- CPU Utilization
- Auto Scaling events
- Instance health

---

## 🔄 Load Testing

CPU load was generated using:
This increases CPU usage and triggers Auto Scaling.

---

## 🔁 Failover Testing

An EC2 instance was manually terminated to test fault tolerance.
Auto Scaling automatically launched a new instance to maintain availability.

---

# 📸 Project Screenshots

### 1. Application Load Balancer Output
![ALB Output 1](https://github.com/Sakshigond12/highly-available-web-app-aws/blob/a141c8c1ab165c0550cb65e706c0f060a2debdaf/img/Application%20Load%20Balancer%20DNS%20output%201.png)


![ALB Output 2](https://github.com/Sakshigond12/highly-available-web-app-aws/blob/a141c8c1ab165c0550cb65e706c0f060a2debdaf/img/Application%20Load%20Balancer%20DNS%20output%202.png)

### 2. Target Group Healthy Instances
![Target Group](https://github.com/Sakshigond12/highly-available-web-app-aws/blob/a141c8c1ab165c0550cb65e706c0f060a2debdaf/img/Target%20group%20health.png)

### 3. EC2 Instances
![EC2 Instances](https://github.com/Sakshigond12/highly-available-web-app-aws/blob/a141c8c1ab165c0550cb65e706c0f060a2debdaf/img/Auto%20Scaling%20Activity%20logs.png)

### 4. Auto Scaling Group Configuration
![ASG](https://github.com/Sakshigond12/highly-available-web-app-aws/blob/a141c8c1ab165c0550cb65e706c0f060a2debdaf/img/Amazon%20EC2%20Auto%20Scaling%20configuration.png)

### 5. CloudWatch Monitoring
![CloudWatch](https://github.com/Sakshigond12/highly-available-web-app-aws/blob/a141c8c1ab165c0550cb65e706c0f060a2debdaf/img/Amazon%20CloudWatch%20CPU%20graph.png)

---
#  🚀Conclusion

This project successfully demonstrates how to build a highly available and scalable web application architecture on AWS. By using EC2, Auto Scaling Group, and Application Load Balancer, the system can automatically handle traffic spikes and maintain application availability. 
The architecture distributes traffic across multiple instances in different Availability Zones and automatically replaces unhealthy instances, ensuring reliability and eliminating single points of failure.

---
## 👩‍💻 Author

**Sakshi Gond**

Aspiring Cloud & DevOps Engineer  

🔗 GitHub: https://github.com/Sakshigond12  
🔗 LinkedIn: https://linkedin.com/in/sakshi-gond-9ab9092a2
