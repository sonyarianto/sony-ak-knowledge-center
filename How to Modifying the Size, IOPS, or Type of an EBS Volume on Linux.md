Just read here:
- http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-expand-volume.html
- https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/recognize-expanded-volume-linux.html
- 

Or I experience this. I have EC2 (m3.medium) with only 50GB space and I need to expand to 70GB.

- Go to EC2 on AWS and go to Volume section (on the left) and see on all active volume. Choose volume that you want to expand and right-click to choose 'modify' option.
- Enter desired size and wait little bit.
- Next go to EC2 via SSH and do this
- Type `sudo file -s /dev/xvd*`
It will show
```
[root@ip-172-31-46-10 ~]# sudo file -s /dev/xvd*
/dev/xvde: Linux rev 1.0 ext4 filesystem data (needs journal recovery) (extents) (large files) (huge files)
```

So the `/dev/xvde` is the volume that we want to expand.
- Now do this, type
```
sudo resize2fs /dev/xvde
```
and wait little bit.
- Then type `df -h` and see now your volume already increased from 50 GB to 70 GB
