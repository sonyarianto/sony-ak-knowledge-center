Make sure you install WP CLI first then do this.

```
wp plugin install $(wp plugin list --field=name) --force
```

if you are root then do this

```
wp plugin install $(wp plugin list --field=name --allow-root) --force --allow-root
```
