Just my notes as I prepare for the proctored AWS Certified Cloud practicioner.

EC2 -> Instances -> Launch Instance
Fill out the following:

| IP Version | Type | NOTES | 
|------------|------|----------|
| Name       | SSH  | TCP      | 
| Base image      | HTTP | |
| OS      | Amazon Linux | |
| architecture      | 64 bit x86 | |
| instance type      | t2.micro | |
| key pair name     | my_key | |
| key pair type     | RSA | |
| Private Key formate     | *. pem | ppk for win7 or 8, pem for everything else|
| Security Group     | Allow SSH from Anywhere 0.0.0.0/0 | |
| Security Group     | Allow HTTP from internet | |
| Configure storage     | 8gb gp3 | |
| User data - optional     | enter code below | |


EBS storage is where you can configure delete upon termination


### 
Go to Advanced Details add this to User Data:

```
#!/bin/bash
# Use this for your user data (script from top to bottom)
# install httpd (Linux 2 version)
yum update -y
yum install -y httpd
systemctl start httpd
systemctl enable httpd
echo "<h1>Hello World from $(hostname -f)</h1>" > /var/www/html/index.html
```
go to:

Public IPv4 address
 xxx.xxx.xxx.xxx |open address 

And open the link.  Make sure it's http://xxx.xxx.xxx.xxx

Note, it has to be http and not https!


38. Security Groups Hands on

Network Security -> Security Groups
Inbound rules

Inbound rules must be

| IP Version | Type | Protocol | Port | Source     |   Purpose   |
|------------|------|----------|------|------------|-------------|
| IPv4       | SSH  | TCP      | 22   | 0.0.0.0/0  |     ssh     |
| IPv4       | HTTP | TCP      | 80   | 0.0.0.0/0  | web browser |
| IPv6       | SSH | TCP      | 22   | /0  | ssh some |

Purpose:
* Timeout: Caused by security group rules
* Refused:


```
 chmod 0400 *pem
```

which should get: `-r--------``


Commands
aws --version
aws iam list-users


```
 ssh -v -i <private_key>.pem ec2-user@<ip>
````
DO NOT use your username, you must use ec2-user.


# Security risk

`aws configure` via command line
And so as a rule of thumb, never, ever, ever enter your IAM APA key. So the Access Key ID and the Secret Access key into an EC2 Instance. This is horrible and if you see someone doing it,

use IAM
