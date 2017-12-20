```js
process.argv.forEach(function (val, index, array) {
  console.log(index + ': ' + val);
});
```

or

```js
console.log(process.argv[1]);
```
