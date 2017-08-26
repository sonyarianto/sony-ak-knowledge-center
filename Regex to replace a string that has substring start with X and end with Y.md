I have a string like this.

```
http://assets.kompas.com/crop/0x0:1000x667/780x390/filters:watermark(data/photo/2017/08/01/30988886823.png,0,-0,1)/data/photo/2017/08/24/8478682671.jpg
```

and I want to delete this part

```
/filters:watermark(data/photo/2017/08/01/30988886823.png,0,-0,1)
```

and I want the end result like this.

```
http://assets.kompas.com/crop/0x0:1000x667/780x390/data/photo/2017/08/24/8478682671.jpg
```

So the regex would be like this.

```php
$re = '/\/filters(.*?)\)/';
$str = 'http://assets.kompas.com/crop/0x0:1000x667/780x390/filters:watermark(data/photo/2017/08/01/30988886823.png,0,-0,1)/data/photo/2017/08/24/8478682671.jpg';
$subst = '';

$result = preg_replace($re, $subst, $str, 1);

echo "The result of the substitution is ".$result;
```
