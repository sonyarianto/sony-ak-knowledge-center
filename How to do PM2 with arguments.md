Well there are 2 ways you can do to pass the parameters from pm2 to nodejs in CLI:

```
pm2 start app.js -- dev --port=1234 (note there is an extra space between -- and dev)
```
or
```
pm2 start app.js --node-args="dev --port=1234"
```

Both ways, you will find these values exist in process.argv (['dev','--port=1234'])
