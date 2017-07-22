Create the repo definition.

```
vi /etc/yum.repos.d/google-chrome.repo
```

Then add this.

```
[google-chrome]
name=google-chrome - \$basearch
baseurl=http://dl.google.com/linux/chrome/rpm/stable/\$basearch
enabled=1
gpgcheck=1
gpgkey=https://dl-ssl.google.com/linux/linux_signing_key.pub
```

Then test it with this.

```
yum search google-chrome
```

It will show like below.

```
Loaded plugins: fastestmirror
Loading mirror speeds from cached hostfile
 * base: mirror.sesp.northwestern.edu
 * epel: mirror.steadfast.net
 * extras: denver.gaminghost.co
 * ius: dfw.mirror.rackspace.com
 * updates: centos.firehosted.com
=========================================================================== N/S matched: google-chrome ============================================================================
chrome-remote-desktop.x86_64 : Remote desktop support for google-chrome & chromium
google-chrome-beta.x86_64 : Google Chrome (beta)
google-chrome-stable.x86_64 : Google Chrome
google-chrome-unstable.x86_64 : Google Chrome (unstable)

  Name and summary matches only, use "search all" for everything.
```

OK it means Google Chrome is ready to install. Just install the stable version.

```
yum install google-chrome-stable
```

Check the version with this.

```
google-chrome --version
```
On mine will show this.
```
Google Chrome 59.0.3071.115
```
