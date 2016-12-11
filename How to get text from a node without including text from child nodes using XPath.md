Look this markup.

```html
<div id="comment">
      <div class="title">Editor's Description</div>
      <div class="changed">Last updated: </div>
      <br class="clear">
      Lorem ipsum dolor sit amet. 
</div>
```

I want to get string `Lorem ipsum dolor sit amet.`

Here is the way.

```
/div/text()[last()]
```

or better

```
/div/text()[normalize-space()]
```

This selects all text-node-children of /div that are not whitespace-only text nodes.

We cannot use 

```
/div/text()
```

since it will generate multiple nodes that contains whitespace.
