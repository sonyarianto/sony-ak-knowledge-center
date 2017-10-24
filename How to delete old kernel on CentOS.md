```bash
## Install yum-utils ##
## Fedora 25/24/23/22 ##
dnf install yum-utils

## Fedora 21/20/19/18/17/16, CentOS, Red Hat (RHEL) ##
yum install yum-utils

## Package-cleanup set count as how many old kernels you want left ##
package-cleanup --oldkernels --count=2
```
