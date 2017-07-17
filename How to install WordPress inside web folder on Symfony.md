Just do this. I assume you want to install WordPress on folder `blog` on `web` folder.
```
..... 
<IfModule mod_rewrite.c>

    RewriteEngine On
    # wordpress rules 
    DirectoryIndex index.php
    RewriteRule ^blog/(.*)$ blog/$1 [PT,L]

    # symfony rules 
    DirectoryIndex app.php
    .....
```
