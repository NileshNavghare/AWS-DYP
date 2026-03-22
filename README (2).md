
# Deploy Apache Web Server on AWS EC2

This document explains how to create an EC2 instance and deploy a simple Apache Web Server.

---

## Step 1: Launch EC2 Instance

1. Login to AWS Console
2. Go to EC2 Dashboard
3. Click Launch Instance
4. Select configuration:
   - AMI: Amazon Linux
   - Instance type: t2.micro
   - Allow HTTP (port 80) and SSH (port 22)
5. Click Launch Instance

Screenshot:
images/ec2_launch.png

---

## Step 2: Connect to EC2 Instance

ssh -i "key.pem" ec2-user@<Public-IP>

Screenshot:
images/ec2_ssh.png

---

## Step 3: Update Packages

sudo yum update -y

---

## Step 4: Install Apache Server

sudo yum install -y httpd

---

## Step 5: Start Apache Server

sudo systemctl start httpd

---

## Step 6: Enable Apache on Boot

sudo systemctl enable httpd

---

## Step 7: Create Simple Web Page

echo "<h1>Hello from Apache Web Server on EC2</h1>" | sudo tee /var/www/html/index.html

---

## Step 8: Access Website

http://<Public-IP>

Screenshot:
images/apache_output.png

---

## Project Structure

project-folder
│
├── README.md
└── images
    ├── ec2_launch.png
    ├── ec2_ssh.png
    └── apache_output.png

---

## Output

Web server successfully deployed on EC2 instance.
