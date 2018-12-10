# Scenario
We want to get Let's Encrypt SSL certificate using different machine than the webserver. I have Ubuntu 18.04 and I installed certbot.

# How to use?
```
sudo certbot certonly --manual
```

If you have domain let say anu.com then you need specifiy `www.anu.com,anu.com`.

Follow the instruction. Usually you will have to create a file and put it on your webroot for the `anu.com`.
