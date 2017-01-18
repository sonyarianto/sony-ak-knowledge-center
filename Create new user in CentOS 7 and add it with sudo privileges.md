* Login to server with root account
* Create user called `sony` with command below
```
adduser sony
```
* Change password with command below
```
passwd sony
```
* Add user to `wheel` group. By default, on `CentOS`, members of the `wheel` group have sudo privileges.
```
usermod -aG wheel sony
```
* Test the new user, switch to that user
```
su - sony
```
* Type a command to test the sudo privilege
```
sudo ls -la /root
```
