Full-Stack Web App Deployment on AWS
This guide will walk you through the process of deploying a full-stack web application on AWS using Amazon EC2 for hosting and MongoDB for database storage. The application consists of a frontend built with Vite and a backend powered by Node.js.

Pre-requisites
Before getting started, ensure you have the following:

An AWS account
Basic knowledge of AWS services
Access to MongoDB Atlas or a MongoDB instance
Deployment Steps

1. Create VPC
   Log in to your AWS Management Console.
   Navigate to the VPC service.
   Create a new Virtual Private Cloud (VPC) with appropriate configurations.
2. Check Security Group
   Configure security groups to allow traffic to your EC2 instance.
3. Create EC2 Instance
   Launch an EC2 instance with Amazon Linux AMI, choosing the previously created VPC and security group.
4. Connect to EC2 Instance
   Use Git Bash or a terminal with your personal key pair to connect to the EC2 instance.
5. Set up MongoDB
   Set up MongoDB using a hosted solution like MongoDB Atlas.
   Configure network access to allow connections from your EC2 instance (add ec2 public address to your database Security/Network Access).
6. Fork and Configure the Repository
   Fork this repository to your GitHub account.
   Update the public IP address manually in the frontend/src/pages 5 files.
   Modify the MongoDB connection URL in the backend configuration file (backend/config.js) to point to your MongoDB instance.
7. Install Git
   On the EC2 instance, install Git using the following command:
   sudo yum install git
8. Clone and Set up the Repository
   Clone your forked GitHub repository onto your EC2 instance:
   git clone <your-forked-github-repo-url>
   cd BookStore-MERN
9. Install Node.js and npm
   Install Node.js using Node Version Manager (nvm), you can use this link: https://nodejs.org/en/download/package-manager , or use following commands:
   curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
   Shutdown and reopen the EC2 instance.
   Install Node.js:
   nvm install 20
   Verify installation:
   node -v
   npm -v
10. Setup Frontend
    Navigate to the frontend directory and install dependencies:
    cd frontend
    npm install -g vite
    npm install
    npm run dev -- --host
11. Setup Backend
    Open another terminal (bash) for backend.
    Connect to the EC2 instance and navigate to the backend directory:
    cd BookStore-MERN/backend
    npm install
    npm run dev -- --host
12. Access the Web Application
    Access the hosted full-stack website through the following link:
    http://<ec2-public-ip>:<port>
13. Clear AWS Resources
    Remember to clear AWS resources when done to avoid unnecessary charges.

Contributing
Contributions are welcome! Please feel free to fork the repository, make changes, and submit pull requests.

License
This project is licensed under the MIT License.
