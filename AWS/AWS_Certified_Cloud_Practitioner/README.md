Just my notes as I prepare for the proctored AWS Certified Cloud practicioner.






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
