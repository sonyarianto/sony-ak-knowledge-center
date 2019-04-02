Scenario like this, I logged-in as root and on root there are several entries on crontab, so do this.

```
crontab -l > my_crontab.backup
```

It will backup to file my_crontab.backup on current directory.

Other scenario, I am on root and I have entries of crontab on user sony, so do this.

```
crontab -l -u sony > my_crontab.backup
```
