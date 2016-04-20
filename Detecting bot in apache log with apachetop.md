I am using CentOS.

Install `apachetop` using `yum install apachetop`.

Run the `apachetop` by typing below.

```bash
apachetop -f /your/location/of/access_log
```

Get the high traffic from some IPs.

Then get the IP details using this command.

```bash
grep "IP_ADDRESS" /your/location/of/access_log
```

Now you will get the detail of the bot name. If you want to block it, just add it to your `ip_tables` rule like below.

```bash
-A INPUT -s 5.9.7.208/32 -j DROP
```
