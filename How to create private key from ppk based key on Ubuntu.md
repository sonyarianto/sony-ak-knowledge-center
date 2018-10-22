First install `sudo apt-get install putty-tools`

Then do this.

To generate the private key:

```
puttygen id_dsa.ppk -O private-openssh -o id_dsa
```

and to generate the public key:

```
puttygen id_dsa.ppk -O public-openssh -o id_dsa.pub
```
