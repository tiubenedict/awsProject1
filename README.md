# Hosting a static website on Amazon S3
## 🌍 Overview
This project demonstrates how to set up a static website using AWS services. The goal is to quickly host a website using S3 buckets, while testing other features like timed presigned URLs, bucket policies, bucket versioning, and linking it with Amazon Route 53 to register your own domain.

## 🏗️ Architecture
<img src="https://github.com/tiubenedict/awsProject1/blob/bde448b70d688abb4ca1035a2e5361b1cfbc1fb9/diagram.drawio.png" width="25%">

## 🧱 Setup Instructions
### Step 0: Register a domain with Route 53
1. Log in to your AWS Management Console
2. Navigate to the Route 53 service
3. Purchase desired domain
### Step 1: Create an S3 Bucket and link it to your domain on Route 53
1. Navigate to the S3 service
2. Click on "Create bucket", use the exact name as your domain, and follow the prompts to create a new bucket
3. Enable Static Website Hosting, and choose your root html file, e.g. `index.html`
4. Navigate to Route 53 service and click on the default Hosted Zone
5. Click on "Create a new record", click on "Switch to wizard", choose "simple routing policy", and follow the prompts
### Step 2: Upload html files
1. Navigate to your bucket
2. Click the "Upload" button
3. Upload your index.html and related folders that contain any css, images, scripts
### Step 3: Set the files to public
1. Navigate to your bucket
2. Click the checkbox on index.html and other folders
3. Under Actions dropdown, click on "Make public using ACL"
### Step 4: Timed Presigned URLs for specific files
1. Upload the desired file into your S3 bucket
2. Click the checkbox for that file
3. Under Actions dropdown, click on "Share with a presigned URL" and input desired duration

## 🛠️ Configuration Details
### S3 Bucket Configuration
- Bucket Name: same as purchased domain (or any bucket name if not using your Route 53 domain)
- Region: ap-southeast-2
- Public Access: Enabled
- ACL: Enabled
- Versioning: Enabled
- Static Website Hosting: Enabled

### Route 53 Domain Configuration
- Record type: A
- Endpoint: Alias to S3 website endpoint
- Region: same as above
- Evaluate Target Health: Off

## 🍽️ Usage Instructions
- Access the S3 bucket at the domain purchased (or at URL given at Properties > Static Website Hosting, if not using your Route 53 domain)

## 🚨 Troubleshooting
### Common Issues
- **Issue 1:** Unable to access S3 bucket.

  - **Solution:** Check the bucket's public access settings and ensure the bucket policy allows public access.

- **Issue 2:** "No target available" when linking Hosted Zone to S3 bucket.

  - **Solution:** Ensure that Static Website Hosting has been enabled first, and that your bucket name follows your domain name exactly, as in `sample-domain.com`
