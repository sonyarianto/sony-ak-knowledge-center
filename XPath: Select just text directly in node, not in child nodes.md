How does one retrieve the text in a node without selecting the text in the children?
```html
<div id="comment">
     <div class="title">Editor's Description</div>
     <div class="changed">Last updated: </div>
     <br class="clear">
     Lorem ipsum dolor sit amet.
</div>
```
In other words I want `Lorem ipsum dolor sit amet.` rather than `Editor's DescriptionLast updated: Lorem ipsum dolor sit amet.`

```php
$xPathQuery = $xPathDoc->query("(//table[@class='data-tables']//tbody//tr)[1]/td[5]/text()[last()]");
```
The key is the `.../text()[last()]` component.
