Scenario:
You have images like these, served from WordPress.

```
http://anu.com/images/haha-300x230.jpg
http://anu.com/images/hoho-300x150.png
```

You want to make it like these.

```
http://anu.com/images/haha.jpg
http://anu.com/images/hoho.png
```

Then my PHP code is like this.

```
$pos = strpos($image, "-300x");
if(!($pos === false)) {
  $pos = strrpos($image, "-");
  $ext = substr($image, $pos);
  $ext = substr($ext, strpos($ext, '.'));

  $image = substr($image, 0, $pos) . $ext;
}
```
