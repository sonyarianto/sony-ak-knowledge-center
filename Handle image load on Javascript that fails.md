If you're running this after the image already has a set source, you need to do an additional check for caches images (who fired the event, just before you added an event handler listening for it). You can do that like this:

```js
$("#myimageid").on('load', function() {
  alert('Image Loaded'); 
}).each(function() {
  if(this.complete) $(this).load();
});
```

or

```js
$("#myimageid").on('load', function() {
  alert('Image Loaded'); 
}).each(function() {
  if(this.complete) {
    alert('Image Loaded from Cache');
  }
});
```
