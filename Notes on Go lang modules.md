For example, I do this from any folder (non GOPATH folder)

```
go get github.com/arangodb/go-driver
```

Then I got this.

```
go: cannot find main module; see 'go help modules'
```

Hmmmm, first I have go version below.

```
go version go1.11.4 linux/amd64
```

So after research on Google, I do this.

```
export GO111MODULE=auto
```

Then repeat again.

```
go get -v github.com/arangodb/go-driver
```

Then voila, now it works like below.

```
github.com/arangodb/go-driver (download)
github.com/arangodb/go-velocypack (download)
github.com/arangodb/go-driver/util
github.com/arangodb/go-velocypack
github.com/arangodb/go-driver
```

So when you use Go version 1.11.x I think the modules part make many people confuse including me.
