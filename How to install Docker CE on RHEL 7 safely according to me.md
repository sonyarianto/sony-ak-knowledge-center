Follow the requirement on Docker web here https://docs.docker.com/install/linux/docker-ce/centos/

Then I go here
```
yum install --setopt=obsoletes=0 \
   docker-ce-17.03.2.ce-1.el7.centos.x86_64 \
   docker-ce-selinux-17.03.2.ce-1.el7.centos.noarch # on a new system with yum repo defined, forcing older version and ignoring obsoletes introduced by 17.06.0
```

Read here as well https://stackoverflow.com/questions/45272827/docker-ce-on-rhel-requires-container-selinux-2-9

Go to here https://centos.pkgs.org/7/centos-extras-x86_64/

Install the container-selinux (the latest one) e.g.

```
yum install http://mirror.centos.org/centos/7/extras/x86_64/Packages/container-selinux-2.68-1.el7.noarch.rpm
```

After that I think it's OK.
