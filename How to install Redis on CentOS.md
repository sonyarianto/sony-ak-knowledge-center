Download Redis latest stable version. Do not use your Linux distribution Redis package since it quite old.
```bash
wget http://download.redis.io/redis-stable.tar.gz
tar xvzf redis-stable.tar.gz
cd redis-stable
make
```
Follow steps for proper installation using `initscripts` on http://redis.io/topics/quickstart read on section `Installing Redis more properly`

When you type this command `sudo update-rc.d redis_6379 defaults` and you failed then modify the header of file
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
Now your Redis will start on next CentOS boot.
OK now test to run the redis server by typing
```
/etc/init.d/redis_6379 start
```
then try the connection by typing
```
redis-cli ping
```
if everything OK then Redis will reply with string `PONG`.
