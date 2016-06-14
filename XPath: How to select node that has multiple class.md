Suppose markup like below.
```html
<div class="class1 class2">
  <p>Content</p>
</div>
```
You want to select `div` that contains class called `class1`. So the XPath is like below.
```xpath
//div[contains(@class, 'class1')]
```
