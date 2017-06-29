Suppose you have markup like below.
```html
<div class="information">
<b>My Name is Sony</b>
and I was born in Singaraja, Bali
</div>
```
You want to get string `and I was born in Singaraja, Bali` and it's very easy. Try this XPath.
```xpath
(//div[@class='information'])[1]/b/following-sibling::text()[1]
```
