```
sudo amazon-linux-extras install docker
sudo systemctl start docker
sudo systemctl enable docker

// I assume you are in ec-user now
sudo usermod -a -G docker ec2-user
```

Try with run this command
```
docker ps
```

If no `permission` error then I think everyting OK.

Now install Docker Compose, follow instruction at https://docs.docker.com/compose/install/
