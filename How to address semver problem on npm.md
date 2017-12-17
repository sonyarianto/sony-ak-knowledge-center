I had the same error. npm uninstall npm -g, rm -rf node_modules didn't help me, because when I tried I was getting Error: Cannot find module 'semver'. But I solve my problem with these steps:

```
    sudo rm -rf /usr/local/lib/node_modules
    sudo rm -rf ~/.npm
    brew uninstall --force node
    brew install node
```

Hope this will help those who are getting a similar problem.
