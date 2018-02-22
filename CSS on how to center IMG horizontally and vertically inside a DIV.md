```html
<div class="a_div"><img class="img_inside_div" src="your_image.png"></div>
```

```css
.a_div {
width:100%;
height:200px;
background-color:#eee;
border-radius:3px;
overflow:hidden;
position:relative;
}

.img_inside_div {
width:100%;
height:auto;
text-align:center;
position:absolute;
top:0;
bottom:0;
margin:auto;
min-height:50px;
}
```
