Suppose markup like below.
```html
<select id="select">
  <option value="1" data-foo="dogs">this</option>
  <option value="2" data-foo="cats">that</option>
  <option value="3" data-foo="gerbils">other</option>
</select>
```
So the code to detect additional data during `onchange` is like below.
```javascript
// javaScript using jQuery
$(function(){
    $('select').change(function(){
       var selected = $(this).find('option:selected');
       var extra = selected.data('foo'); 
       ...
    });
});
```
