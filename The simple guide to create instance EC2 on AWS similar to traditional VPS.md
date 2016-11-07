1. Create EC2 instance, choose specifications etc.
2. On the last steps you will offered to create new keypair and download the .pem file.
3. If you want to connect using `Putty` you will convert the .pem file become .ppk file using `puttygen` tool.
4. Connect to your EC2 instance through SSH using `ec2-user` user and hostname provided by your EC2 instance and set the Auth/private key using the .ppk file
5. If everything OK then you will be able to connect to your EC2 instance and to become `root` just type `sudo su`.
6. Your EC2 instance is ready and you can install anything (setup additional user, setup web server, setup database etc).
