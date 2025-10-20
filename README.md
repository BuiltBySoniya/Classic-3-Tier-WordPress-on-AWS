# 🚀 Classic 3-Tier WordPress on AWS

Traditional Web Architecture for WordPress Deployment

## Short Description

Built a highly available 3-tier architecture on Amazon Web Services to host a WordPress website. The design emphasises scalability, security and operational best practices by separating the presentation, application and database layers across multiple availability zones.

## 🛠️ AWS Services Used:

Amazon VPC,
Internet Gateway (IGW),
NAT Gateway,
Application Load Balancer (ALB),
Amazon EC2,
Amazon RDS,
IAM Roles & Policies

## 🧰 Technical Tools:

Linux EC2 (Ubuntu/Amazon Linux),
WordPress (PHP + MySQL),
SSH/Putty for connectivity,
AWS CLI & Console

## 🧠 Skills Demonstrated:

Designing multi-layer cloud infrastructure,
Deploying WordPress in a secure environment,
Configuring high-availability and load-balancing,
Applying best practices for network design and security

## 📋 Steps Performed

### 1. Networking Setup – Create a VPC with Public & Private Subnets

Created a VPC with CIDR block 10.0.0.0/16 and enabled DNS hostnames. Defined two public subnets (for ALB/NAT) and four private subnets (two for app tier and two for database tier) across two AZs.

### 2. Networking Setup – Create a NAT Gateway & Security Groups

Allocated Elastic IPs and provisioned two NAT Gateways in the public subnets. Configured route tables so private subnets route outbound via NAT while public subnets route via IGW. Created security groups for ALB (HTTP/HTTPS), web servers (HTTP from ALB), database (MySQL from web servers) and SSH access limited to your IP.

### 3. Database Setup – Create MySQL Database and EFS in AWS

Defined an RDS MySQL instance in the private DB subnets with no public access, using a DB subnet group. Created an Amazon EFS file system in the private subnets for shared storage used by WordPress across EC2 instances.

### 4. Compute Setup – Setting Up EC2 Instances and Application Load Balancer

Launched two EC2 instances in the private application subnets running WordPress (PHP/Apache) connecting to the RDS database and mounting EFS. Created an Internet-facing ALB in public subnets routing traffic to the web servers. Associated the ALB with the web-server security group and registered instances as targets.

## ✅ Final Result:

Live WordPress Website on a Production-Ready 3-Tier Architecture

## 💼 Business Implication:

By deploying WordPress on a three-tier architecture in AWS, organisations gain a robust, scalable, and secure web hosting foundation. This separation of concerns—web layer, application layer and data layer—enables better fault-tolerance, easier management of updates and backups, and allows your infrastructure to support growth, traffic spikes and long-term reliability without compromising on performance or security.
