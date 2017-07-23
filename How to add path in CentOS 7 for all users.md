Create `.sh` file in `/etc/profile.d/` directory.

For example like this.

```
vi /etc/profile.d/mypath.sh
```

and suppose you want to add your own path (e.g. /usr/local/bin) information just add this to the file.

```
export PATH=$PATH:/usr/local/bin
```

Save it, exit from current shell and login again and then to test it type this.

```
echo $PATH
```

See yourself.
