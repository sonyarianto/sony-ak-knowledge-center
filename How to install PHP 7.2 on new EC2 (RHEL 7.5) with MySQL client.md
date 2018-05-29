I try EC2 free-tier (t2.micro) using Linux RHEL 7.5 on AWS and I want to use it as an aggregator agent. So I need this spec:

* PHP 7.2 installed
* MySQL client installed

This is what I do.

1. Launch EC2, I choose RHEL 7.5 with free-tier settings (t2.micro, 30 GB EBS volume)
2. First I logged-in to ec2-user (use SSH with private key to login)
3. Do `sudo su`
4. Do `yum update`
5. Do `yum install mysql` to install MySQL client
6. Do read this because I am lazy hahahaha https://rpms.remirepo.net/wizard/
