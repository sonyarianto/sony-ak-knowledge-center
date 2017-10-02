See this example.

```
tail -F /var/log/nginx/web/access.log | grep -v Googlebot
```

It will show all lines that not contains `Googlebot` string.
