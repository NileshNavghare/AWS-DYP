
# Deploy Apache Web Server on AWS EC2 (Step-by-Step with Outputs)

This guide explains how to create an AWS EC2 instance and deploy a simple Apache Web Server on it.

---

## Prerequisites

- AWS Account
- Key Pair (.pem file)
- Internet connection
- Basic knowledge of Linux commands

---

## Step 1: Login to AWS Console

Go to AWS Management Console.

Service → EC2 → Launch Instance

### Configuration
- Name: Apache-Server
- AMI: Amazon Linux
- Instance Type: t2.micro
- Key Pair: select or create new
- Allow:
  - SSH (22)
  - HTTP (80)

### Output
EC2 instance successfully created and running.

---

## Step 2: Connect to EC2 Instance

Open Command Prompt / Terminal and run:

ssh -i "key.pem" ec2-user@<Public-IP>

### Output
Connected to EC2 Linux terminal.

Example:
[ec2-user@ip-172-31-xx-xx ~]$

---

## Step 3: Update Linux Packages

Command:

sudo yum update -y

### Output
System packages updated successfully.
List of packages will be downloaded and installed.

---

## Step 4: Install Apache Web Server

Command:

sudo yum install -y httpd

### Output
Apache HTTP Server installed successfully.

---

## Step 5: Start Apache Service

Command:

sudo systemctl start httpd

### Output
Apache service started.

Check status:

sudo systemctl status httpd

Output:
active (running)

---

## Step 6: Enable Apache Service at Boot

Command:

sudo systemctl enable httpd

### Output
Apache service enabled at system startup.

---

## Step 7: Create Simple Web Page

Command:

echo "<h1>Welcome to Apache Web Server on AWS EC2</h1>" | sudo tee /var/www/html/index.html

### Output
HTML file created successfully.

---

## Step 8: Access Web Server

Open browser and enter:

http://<Public-IP>

### Output
Web page displayed:

Welcome to Apache Web Server on AWS EC2

---

## Final Script (All Commands Together)

#!/bin/bash
sudo yum update -y
sudo yum install -y httpd.x86_64
sudo systemctl start httpd.service
sudo systemctl enable httpd.service

---

## Project Structure

project-folder
│
├── README.md
└── images (optional screenshots)

---

## Conclusion

Apache Web Server successfully deployed on AWS EC2 instance.


change the default Apache web page content to:

WELCOME TO DY PATIL UNIVERSITY PUNE, AMBI

This modifies the default file index.html in the Apache web server directory of Apache HTTP Server running on Amazon EC2.
echo "<h1>WELCOME TO DY PATIL UNIVERSITY PUNE, AMBI</h1>" | sudo tee /var/www/html/index.html
