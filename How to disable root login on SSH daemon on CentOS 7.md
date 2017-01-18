* Login to server
* Edit the config
```
vi /etc/ssh/sshd_config
```
* Search for 
```
#PermitRootLogin yes
```
* Change it to 
```
PermitRootLogin no
```
* Save it then restart the SSH daemon
```
systemctl reload sshd
```
