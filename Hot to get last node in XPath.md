Suppose you have markup like below.

```html
<div id="comment">
      <div class="title">Editor's Description</div>
      <div class="changed">Last updated: </div>
      <br class="clear">
      Lorem ipsum dolor sit amet. 
</div> 
```

and you want to get string `Lorem ipsum dolor sit amet.` so the XPath should be like below

```xpath
/div/text()[last()]
```
