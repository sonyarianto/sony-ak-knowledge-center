Error example
```
W: GPG error: http://dl.google.com stable Release: The following signatures couldn't be verified because the public key is not available: NO_PUBKEY A040830F7FAC5991
```
Solution
```
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys [key here]
```
