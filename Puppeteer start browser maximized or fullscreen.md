Maximized
```js
const browser = await puppeteer.launch({
    headless: false,
    args: ['--start-maximized']
  });
```

Fullscreen
```js
const browser = await puppeteer.launch({
    headless: false,
    args: ['--start-fullscreen']
  });
```

More detail at https://peter.sh/experiments/chromium-command-line-switches/
