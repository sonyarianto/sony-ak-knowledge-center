First
```
grep -E 'Baiduspider' access_log
```
then read the IP address then add it to iptables then
```
sed -i "/\b\(xxx.xxx.xxx.\)\b/d" access_log
```
where `xxx.xxx.xxx` is the IP address until third octet.
