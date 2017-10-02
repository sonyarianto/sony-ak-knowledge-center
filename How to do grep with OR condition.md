Doing grep that contains string `spider`, `bot`, `Yahoo`, `baidu` or `YandexBot`.
```
tail -F /example/your/access_log | grep -E 'spider|bot|Yahoo|baidu|YandexBot'
```

Doing grep that contains string  `spider`, `bot`, `Yahoo`, `baidu`, `YandexBot`, `rogerbot` or `MetaURI` and exclude string that contains `Googlebot`.
```
tail -F /var/log/nginx/web/access.log | grep -v Googlebot | grep -E 'spider|bot|Yahoo|baidu|YandexBot|rogerbot|MetaURI'
```
