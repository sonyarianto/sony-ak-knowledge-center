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
* Add this config
```
AllowUsers your_prefer_user
```
* Save it then restart the SSH daemon
```
systemctl reload sshd
```
