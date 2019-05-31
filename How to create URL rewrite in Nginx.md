- https://www.nginx.com/blog/creating-nginx-rewrite-rules/
- https://support.modx.com/hc/en-us/articles/217295387-Web-Rules-Rewrites

Sample
```
rewrite ^/listings/(.*)$ /listing.html?listing=$1 last;
```
