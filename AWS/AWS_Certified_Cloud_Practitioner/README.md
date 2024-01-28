Just my notes as I prepare for the proctored AWS Certified Cloud practicioner.


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




38. Security Groups Hands on

Network Security -> Security Groups
Inbound rules

Inbound rules must be

| IP Version | Type | Protocol | Port | Source     |   Purpose   |
|------------|------|----------|------|------------|-------------|
| IPv4       | SSH  | TCP      | 22   | 0.0.0.0/0  |     ssh     |
| IPv4       | HTTP | TCP      | 80   | 0.0.0.0/0  | web browser |


Purpose:
* Timeout: Caused by security group rules
* Refused:


```
 chmod 0400 *pem
```

which should get: `-r--------``
