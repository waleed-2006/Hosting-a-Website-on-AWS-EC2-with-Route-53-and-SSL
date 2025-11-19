# Hosting-a-Website-on-AWS-EC2-with-Route-53-and-SSL


**1. Launch an EC2 Instance**

.Open AWS Console → EC2 → Launch Instance

.Select Ubuntu Server (LTS)

.Create/download a .pem key pair

.Configure Security Group:

.SSH (22) → Your IP

.HTTP (80) → Anywhere

.HTTPS (443) → Anywhere

.Launch instance and note your Public IP / Elastic IP

**Launched an EC2 Instance**
-------
![Capture](https://github.com/user-attachments/assets/866c2d3e-10d4-473d-9c31-441fb560dd4d)

**2. Connect to EC2 (using PuTTY/SSH)**
.Download Putty.exe file and install it in your device.

.Go to connection.

.Go to SSH

.Go to Auth

.Choose key pair file you made while creating instance.

``````login as username: ubuntu
``````


**3. Install Apache**
   
``````sudo apt install apache2
Check in browser → http://yourpublicip
``````

An Apache page will be shown to your public ip.

``````cd /var/www/html
sudo rm index.html
sudo vi index.html
``````
Press I to insert your own html code.
Write your own code.
After writing all code , Press Ctrl+C and then write ":wq" and Press Enter.

**4. Map Domain with Route 53**
Register your own domain name.
Go to Route 53 on AWS, Click on Hosted Zones.

**Route 53 Hosted Zone**
-------
![hoseted zone](https://github.com/user-attachments/assets/2c2d59c4-1da5-4952-8a2a-85afdbbf6d2c)
.You will get four NS name server.


**NS Name Servers**
-------
![recerod](https://github.com/user-attachments/assets/ca585638-ef39-4391-85a1-1f2bc2cadc48)


_Then update these name server in your domain.


**Domain Name adding Name server**
------
<img width="3474" height="1877" alt="image" src="https://github.com/user-attachments/assets/eeb0c9d7-d764-4be1-a36c-0cded40be957" />


_Create A record
_Set your domain, Enter your allotted Public IP and then Map it.




**Website before SSL certfication (Showing Not Secure)**
--------
![site](https://github.com/user-attachments/assets/25200e8a-387c-47d3-9ff2-58d7555bc6d9)




**6. Enable SSL (HTTPS) using Certbot**
``````sudo apt update
sudo apt install certbot python3-certbot-apache -y
sudo certbot --apache
``````
Then it will ask an email.
Then it will ask your domain name , So just write it.
Then SSL certification will deployed to your domain name. Check in browser → ``````https://yourpublicip``````


**Website after SSL certfication using https (Showing Connection is Secure)**
------
![ssl site](https://github.com/user-attachments/assets/9dd3d66d-81d2-4476-986f-ce52990daabf)






