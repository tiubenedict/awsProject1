# Amazon S3
Hosting a static website on Amazon S3

## 🌍 Overview
This project demonstrates how to set up a static website using AWS services. The goal is to quickly host a website using S3 buckets.

## 🏗️ Architecture
<img src="https://github.com/tiubenedict/awsProject1/blob/bde448b70d688abb4ca1035a2e5361b1cfbc1fb9/diagram.drawio.png" width="25%">

## 🧱 Setup Instructions
### Step 1: Create an S3 Bucket
1. Log in to your AWS Management Console.
2. Navigate to the S3 service.
3. Click on "Create bucket" and follow the prompts to create a new bucket.
### Step 2: Upload html files
1. Navigate to your bucket
2. Click the "Upload" button
3. Upload your index.html and related folders that contain any css, images, scripts
### Step 3: Set the files to public
1. Navigate to your bucket
2. Click the checkbox on index.html and other folders
3. Under Actions dropdown, click on "Make public using ACL"

## 🛠️ Configuration Details
### S3 Bucket Configuration
- Bucket Name: `network-website-project-bene`
- Region: ap-southeast-2
- Public Access: Enabled
- ACL: Enabled
- Versioning: Enabled
- Static Website Hosting: Enabled

## 🍽️ Usage Instructions
- Access the S3 bucket at the URL given at Properties > Static Website Hosting.
