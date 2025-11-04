# Hosting-a-Website-on-AWS-EC2-with-Route-53-and-SSL
🚀 Steps from the Repository
1. Launch an EC2 Instance

Log in to your AWS Management Console.

Go to EC2 → Launch Instance.

Choose Ubuntu as the AMI.

Choose an instance type (e.g., t2.micro for free tier).

Configure Security Group:

Allow HTTP (port 80) from anywhere.

Allow HTTPS (port 443) from anywhere.

Allow SSH (port 22) from your IP or anywhere (for testing).

Launch the instance and download the .pem key file.
