# Deploying Portfolio web application on AWS
# Deploying a Web Application on AWS: A Step-by-Step Guide

## Step 1: Local Testing
1. Clone the Repository:
   Clone the project repository from GitHub.
   ```sh
   git clone https://github.com/kartik-paliwa1/Portofolio-API
   ```

2. Set Up Environment Variables:
   Create a `.env` file and configured the necessary environment variables.
   ```plaintext
   DOMAIN=""
   PORT=3000
   STATIC_DIR="./client"
   PUBLISHABLE_KEY=""
   SECRET_KEY=""
   ```

3. Install Dependencies and Start the Project:
   ```sh
   npm install
   npm run start
   ```

With the application running smoothly on local machine, It will be ready to deploy on AWS.

## Step 2: Setting Up an AWS EC2 Instance

1. Create an IAM User
  
2. Launch an EC2 Instance:
   - **OS Image**: Ubuntu
   - **Instance Type**: t2.micro

3. Create a Key Pair:
   Create a key pair for secure SSH access and downloaded the `.pem` file.

4. Connect to the EC2 Instance:
   Using the key pair, connect to the EC2 instance via SSH.
   ```sh
   ssh -i key-pair.pem ubuntu@<IP_ADDRESS>
   ```

## Step 3: Configuring the Remote VM

1. Update Packages:
   ```sh
   sudo apt update
   ```

2. Install Git, Node.js, and npm:
     ```sh
    sudo apt install git
    sudo apt install nodejs
    sudo apt install npm 
   ```


## Step 4: Deploying the Project on AWS

1. Clone the Repository:
   I cloned the project repository on the remote VM.
   ```sh
   git clone https://github.com/kartik-paliwa1/Portofolio-API
   ```

2. **Set Up Environment Variables**:
  Create a `.env` file on the remote VM and configured the environment variables.
   ```plaintext
   DOMAIN=""
   PORT=3000
   STATIC_DIR="./client"
   PUBLISHABLE_KEY=""
   SECRET_KEY=""
   ```
   For this project, I set up an Elastic IP Address for the EC2 instance and used it as the DOMAIN variable.

3. Install Dependencies and Start the Project:
   ```sh
   npm install
   npm run start
   ```

4. Update Security Group Inbound Rules:
   I edited the security group inbound rules to allow traffic through the specified port, ensuring that the application was accessible from the internet.

## Conclusion

Deploying a web application on AWS was a rewarding experience that enhanced my understanding of cloud infrastructure and DevOps practices. By following these steps, you too can deploy your application and make it accessible to users worldwide. Whether you are a developer or aspiring DevOps engineer, mastering the deployment process on AWS is an invaluable skill that will serve you well in your career.

Happy deploying! 🚀
