Logged for any user.

Type below command.

```
vi ~/.bashrc
```

Add this as example of alias command.

```
alias myalias="sshpass -f <(printf '%s\n' YOUR_PASSWORD_HERE) ssh user@host.com"
```

Save it and close the current terminal console to take effect.

Later you can run the command `myalias` from your shell.
