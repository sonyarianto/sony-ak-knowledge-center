I have like this.
```html
<div>
<p>aku</p>
<p>suka</p>
<p>kamu</p>
</div>
```

Do this to get `aku` `suka` `kamu`

```
//div/descendant::*/text()
```

but if have this and want to exclude `style` text then do later.
```html
<div>
<style>body {color:red}</style>
<p>aku</p>
<p>suka</p>
<p>kamu</p>
</div>
```

```
//div/descendant::*[not(self::style)]/text()
```
