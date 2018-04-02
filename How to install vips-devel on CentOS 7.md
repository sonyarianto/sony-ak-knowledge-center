I already build libvips from source (version 8.6.3) and I want to use it from PHP (php binding) so I need

```
pecl install vips
```

But it error on CentOS 7, since CentOS doesn't have `libvips-devel` or `vips-devel`.

I am trying

```
yum install libvips-devel
```
or
```
yum install vips-devel
```

but all not working.

So just read this https://centos.pkgs.org/7/remi-x86_64/vips-devel-8.6.3-1.el7.remi.x86_64.rpm.html
