I prepare 2 (two) CentOS 7 hosts. One with public IP and other private IP.

Install Ansible on both hosts.

On private host go to `/etc/ansible/hosts` and add group

```
[web]
x.x.x.x
```

`x.x.x.x` is public IP host

After that I have this command to `ping` from private to public IP.

```
ansible all -m ping -k -u sony --ask-become-pass
```

Next try an arbitrary command

```
ansible all -m shell -k -u sony -a 'uname -a' --ask-become-pass
```
