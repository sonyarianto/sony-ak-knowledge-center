Scenario:

I want to update my Ubuntu with `sudo apt-get update` then `sudo apt-get upgrade`.

Error appear like below.

```
E: Could not get lock /var/lib/dpkg/lock-frontend - open (11: Resource temporarily unavailable)
E: Unable to acquire the dpkg frontend lock (/var/lib/dpkg/lock-frontend), is another process using it?
```

I solve it with this article.

https://itsfoss.com/could-not-get-lock-error/
