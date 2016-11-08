**Notes:**

1. Both machine should be rsync ready (check with typing `rsync` on both machine)

**Command Sample:**

```
rsync -az -e "ssh -i rsync_key" /var/www/data.zip user@xxx.xxx.xxx.xxx:/home/user
```

Above command will transfer `data.zip` file to remote host using private key.

Private key is prepared using ssh-keygen and install the pub key on the authorized_keys on the target machine.
