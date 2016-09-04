Do this first.
```bash
wget http://download.redis.io/redis-stable.tar.gz
tar xvzf redis-stable.tar.gz
cd redis-stable
make
```
Read here for proper install on initscripts http://redis.io/topics/quickstart
When this command `sudo update-rc.d redis_6379 defaults` failed then modify the header
```
/etc/init.d/redis_6379
```
with
```bash
#!/bin/sh
#
# redis - this script starts and stops the redis daemon
#
# chkconfig:   - 85 15
# description:  Redis is an open source, BSD licensed, advanced \
#               key-value store. It is often referred to as a \
#               data structure server since keys can contain \
#               strings, hashes, lists, sets and sorted sets.
# processname: redis
# config:      /etc/redis/6379.conf
# pidfile:     /var/run/redis_6379.pid
# user:        root
# Simple Redis init.d script conceived to work on Linux systems
# as it does use of the /proc filesystem.
```
then run
```bash
chkconfig --level 2345 redis_6379 on
```
That's it.
