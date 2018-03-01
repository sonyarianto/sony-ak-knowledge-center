I install MongoDB 3.6 on my CentOS 7 machine and I can't connect from other IP.

Relax.

Open `vi /etc/mongod.conf`

Look into `bindIP` setting and usually it still point to `127.0.0.1`.

Just change it to your desired IP address.

Example:
```
bindIp = 192.168.0.177
```

If you want multiple bind to IP addresses, use this example.
```
bindIp = [127.0.0.1, 192.168.184.155, 96.88.169.145]
```
