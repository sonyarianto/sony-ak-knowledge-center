Do this to block IP range.
```
firewall-cmd --permanent --zone=public --add-rich-rule="rule family=ipv4 source address=141.8.144.0/24 reject"
```

or block single IP address.
```
firewall-cmd --permanent --zone=public --add-rich-rule="rule family=ipv4 source address=141.8.144.5/32 reject"
```

Reload the changes.
```
firewall-cmd --reload
```

Check your newly added rule.
```
firewall-cmd --zone=public --list-rich-rules
```

or with this
```
firewall-cmd --zone=public --list-all
```

To remove rich-rule on firewalld use this example.
```
firewall-cmd --permanent --zone=public --remove-rich-rule="rule family=ipv4 source address=141.8.144.5/32 reject"
```
