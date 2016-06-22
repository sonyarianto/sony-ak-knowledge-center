Put 
```
server_tokens off;
```
on `http` block

Then reload or restart nginx web server by typing `service nginx restart` or `systemctl restart nginx`

To check the server headers and if you see the version, you can fetch the headers live from any console using curl:
```
curl -I http://www.yoursite.com
```
