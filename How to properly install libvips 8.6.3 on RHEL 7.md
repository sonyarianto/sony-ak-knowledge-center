When I install libvips 8.6.3 on RHEL 7 on EC2 AWS I found some errors during the build.

Please make sure do this.

1. `yum groupinstall "Development tools"`
2. `yum install glib2-devel`
3. `yum install gtk+*`
4. `yum install gtk2*`
5. `yum install ImageMagick ImageMagick-devel`
