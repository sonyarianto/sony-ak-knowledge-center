Read this https://stackoverflow.com/questions/50639690/on-npm-install-unhandled-rejection-error-eacces-permission-denied

The cache folders need to be owned by the current user, not root.

```
sudo chown -R $USER:$GROUP ~/.npm
sudo chown -R $USER:$GROUP ~/.config
```

This will give ownership to the above folders when running with normal user permissions (not as sudo).

It's also worth noting that you shouldn't be installing global packages using SUDO. If you do run into issues with permissions, it's worth changing your global directory. The docs recommend:
```
mkdir ~/.npm-global
```
```
npm config set prefix '~/.npm-global'
```
Then updating your PATH in wherever you define that (~/.profile etc.)
```
export PATH=~/.npm-global/bin:$PATH
```
You'll then need to make sure the PATH env variable is set (restarting terminal or using the source command)
