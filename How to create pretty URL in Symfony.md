Suppose you want to do URL like this.
```
http://yourdomain.com/area/dki-jakarta/price_min:100000/price_max:200000/area_min:30/area_max:100/page:6
```

Here is the routing basic
```
/**
 * @Route("/area/{province_slug}/{filters}/", name="app_list_page", requirements={"filters":".+"})
 * @Template()
 */
```
It will get
```
price_min:100000/price_max:200000/area_min:30/area_max:100/page:6
```
to single string and later you can parse it for database processing and rendering.
