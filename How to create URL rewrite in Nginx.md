- https://www.nginx.com/blog/creating-nginx-rewrite-rules/
- https://support.modx.com/hc/en-us/articles/217295387-Web-Rules-Rewrites
- https://www.thegeekstuff.com/2017/08/nginx-rewrite-examples/

Sample
```
rewrite ^/listings/(.*)$ /listing.html?listing=$1 last;
```
