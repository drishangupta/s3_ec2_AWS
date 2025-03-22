# AWS Workshop: Hosting Websites with S3 & EC2

##  Overview
Welcome to the **AWS Hosting Workshop**, where you'll learn how to deploy websites using **Amazon S3 (for static sites)** and **EC2 (for dynamic sites)**. By the end, you'll know when to use each service and how to get started with both. Let's dive in! 💻☁️

##  What You’ll Learn
- **Launch an EC2 instance** and deploy a simple web page
- **Host a static website on S3**
- **Compare EC2 vs. S3** to decide the best hosting option

---

##  Prerequisites
Before we begin, make sure you have:

✅ An **AWS Free Tier** account ([Sign Up Here](https://aws.amazon.com/free/))  
✅ **AWS CLI installed** 
```bash
C:\> msiexec.exe /i https://awscli.amazonaws.com/AWSCLIV2.msi
```
✅ Basic knowledge of **Linux commands**  

---

##  Step 1: Launch an EC2 Instance
📍 **1. Open AWS Console** → Go to **EC2 Dashboard**

📍 **2. Click ‘Launch Instance’** → Choose **Amazon Linux 2 AMI**

📍 **3. Select Instance Type** → Choose **t2.micro (Free Tier)**

📍 **4. Configure Security Group** → Allow **HTTP (port 80)** & **SSH (port 22)**

📍 **5. Launch and Connect via SSH**

```bash
ssh -i your-key.pem ec2-user@your-ec2-public-ip
```

---

##  Step 2: Install Apache & Deploy a Web Page
📍 **1. Update & Install Apache**
```bash
sudo yum update -y
sudo yum install httpd -y
sudo systemctl start httpd
sudo systemctl enable httpd
```
📍 **2. Deploy a Simple HTML Page**
```bash
sudo vim /var/www/html/index.html
```
📍 **3. Copy the contents of the index.html in EC2 folder into the newly created index.html**

📍 **4. Check your public IP in a browser**
```
http://your-ec2-public-ip
```

---

##  Step 3: Host a Static Website on S3
📍 **1. Create an S3 Bucket**
```bash
aws s3 mb s3://my-static-site-bucket --region us-east-1
```
📍 **2. Enable Static Website Hosting** (Go to S3 → Properties → Static Website Hosting → Enable)
📍 **3. Upload Your Website Files**
```bash
aws s3 cp index.html s3://my-static-site-bucket --acl public-read
```
📍 **4. Access Your Site via Bucket URL** 🎉

---

##  EC2 vs. S3: When to Use What?
| Feature  | EC2 | S3 |
|----------|-----|----|
| **Dynamic Websites** | ✅ | ❌ |
| **Static Hosting** | ❌ | ✅ |
| **Auto-Scaling** | ✅ | ❌ |
| **Low Cost** | ❌ | ✅ |

💡 **Use EC2 when:** You need a server for dynamic processing (e.g., PHP, Node.js).  
💡 **Use S3 when:** You just need a fast, scalable way to serve static content.

---

## 🏆Bonus: CloudFront for Faster S3 Hosting
Want even faster delivery? Add **AWS CloudFront** to cache and serve your S3 website globally! 🌍

```bash
aws cloudfront create-distribution --origin-domain-name my-static-site-bucket.s3.amazonaws.com
```

---

##  Q&A & Resources
-  **AWS EC2 Docs:** [Click Here](https://aws.amazon.com/ec2/)
-  **AWS S3 Docs:** [Click Here](https://aws.amazon.com/s3/)
-  **Follow Me for More!**

 Happy Hosting! 
