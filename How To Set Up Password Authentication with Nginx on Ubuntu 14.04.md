This is example to implement Basic Auth realm in Nginx.

Just read at https://www.digitalocean.com/community/tutorials/how-to-set-up-password-authentication-with-nginx-on-ubuntu-14-04

and example to change the basic auth realm password is

```
htpasswd -c /your/htpasswd/folder/.htpasswd youruser
```

which is `youruser` is your existing basic auth realm username.
