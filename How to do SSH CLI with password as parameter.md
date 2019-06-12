You can't.

You have to install `sshpass` first.

```
sudo apt-get install sshpass
```

then do this.

```
sshpass -f <(printf '%s\n' YOUR_PASSWORD_STRING_HERE) ssh USER@YOUR_HOST_ADDRESS
```
