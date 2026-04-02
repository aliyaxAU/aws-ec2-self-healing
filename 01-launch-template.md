# Create the Launch Template

In the first step I launch a new template in EC2. In the EC2 Dashboard I select `Launch template` and call it `self-healing-ec2-template`. I use these settings:

- AMI: `Amazon Linux 2023 AMI`
- Instance type: `t2.micro`
- Security group: http allow port 80 from my IP address
- User data: install Apache automatically

Advanced details:

`#!/bin/bash
yum update -y
yum install -y httpd
systemctl enable httpd
systemctl start httpd
echo "Hello from Auto Scaling instance" > /var/www/html/index.html`

![alt text](<img/AMI set up.png>)

I will use this template in the next step.