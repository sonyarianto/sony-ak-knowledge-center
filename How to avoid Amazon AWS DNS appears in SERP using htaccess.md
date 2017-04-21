This is my scenario.

I have web aaa.com then I have EC2 on AWS let say xxx.ap1.amazonaws.com.

I want to create aaa.com/new-web and actually /new-web is connected using Proxy Reverse to xxx.ap1.amazonaws.com

Problem is on Google SERP, I want aaa.com/new-web but actually it will display xxx.ap1.amazonaws.com/new-web. I don't like it. How to handle it?

Then I put this on .htaccess

```
RewriteEngine On

RewriteCond %{HTTP:X-Forwarded-Host} !aaa.com [NC]
RewriteRule ^(.*)$ http://aaa.com/$1 [R=301,L]
```

On Proxy Reverse environment, when aaa.com/new-web called it will contains HTTP_X_FORWARDED_HOST header, so we use this as condition to make it right.
