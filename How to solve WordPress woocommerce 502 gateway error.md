Please add this on location block.

```
proxy_buffering on;
proxy_buffer_size 128k;
proxy_buffers 4 256k;
proxy_busy_buffers_size 256k;

fastcgi_buffers 16 16k;
fastcgi_buffer_size 32k;
```
