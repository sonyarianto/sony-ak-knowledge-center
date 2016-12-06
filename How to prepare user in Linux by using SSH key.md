**What we have:**

1. AWS
2. EC2 Linux AMI
3. Fresh EC2 instance and can login using `ec2-user` user (and able to do `sudo su` to become root)

**Tasks:**

1. Create linux user called `sony`
2. User able to login through SSH using private key
3. User able to become root

**Notes:**

1. EC2 always provide `ec2-user` as the default user and through this user you can login to your instance for the first time.
2. EC2 also provide the SSH key (in `.pem` format) usually before you launch the instance.
3. If you use Putty then you should convert the `.pem` key to `.ppk` using `PuttyGen` utility.
4. User `ec2-user` is special, you can become `root` by typing `sudo su`.

**Let's go to do it:**

Suppose we want to create user `sony`.

1. Login with `ec2-user`
2. Type

  ```
  useradd -G wheel sony
  ```
  it will create user `sony` that belongs to group called `wheel`
3. Or you can type `useradd sony` if you just want to create user but later you have to type `usermod -a -G wheel sony` to add user `sony` to `wheel` group
4. Additional notes: we will configure to become `root` for only users who belongs to `wheel` group later
5. To confirm point 2 process type `id sony` it will shows like below.

  ```
  [root@ip-10-0-0-72 ~]# id sony
  uid=501(sony) gid=501(sony) groups=501(sony),10(wheel)
  ```
6. Now set `sony` password by typing `passwd sony`
7. Now we will configure to be a root user. Type `visudo` (basically this command is to safely edit file `/etc/sudores`)
8. See around line 98 (type `:set nu` to see the line number) there is below

  ```
  ## Allows people in group wheel to run all commands
  # %wheel        ALL=(ALL)       ALL
  ```
9. Uncomment that so it will looks like below
  
  ```
  ## Allows people in group wheel to run all commands
  %wheel        ALL=(ALL)       ALL
  ```
10. Confirm the process on point 7 - 9 by typing `su - sony` (which means switch user) then after that type `sudo su`. If everything OK then user `sony` now become a `root`.
11. Go to `/home/sony` directory
12. Create `.ssh` directory (by typing `mkdir .ssh`)
13. Create file `authorized_keys` inside the `.ssh` directory (by typing `vi .ssh/authorized_keys`)
14. Copy public key to that file. Please be careful while copy and paste (must be precision)
15. Change ownership of .ssh directory by typing:

  ```
  chown -R sony:sony .ssh/
  ```
16. Change permission by typing:
  
  ```
  chmod 700 .ssh/
  chmod 600 .ssh/authorized_keys
  ```
17. That's it, now you should be able to login to EC2 instance using your `sony` user with private key and also able to become `root`.

 
