Update the WP CLI.
```
wp cli update --allow-root
```

See all installed plugins.

```
wp plugin list --allow-root
```

Results like below.

```
+---------------------+----------+-----------+---------+
| name                | status   | update    | version |
+---------------------+----------+-----------+---------+
| akismet             | active   | none      | 4.0.8   |
| all-in-one-seo-pack | active   | available | 2.6.1   |
| coming-soon         | inactive | none      | 5.0.20  |
| fakerpress          | inactive | none      | 0.4.11  |
| hello               | inactive | none      | 1.6     |
| redirection         | active   | available | 3.3.1   |
| td-composer         | active   | none      | 1.0     |
| td-social-counter   | active   | none      | 4.2     |
| wordpress-importer  | active   | none      | 0.6.4   |
+---------------------+----------+-----------+---------+
```

Update each plugin.

```
wp plugin update all-in-one-seo-pack --allow-root
```

See the current WordPress version.

```
wp core version --allow-root
```

Result like below.
```
4.9.7
```

Check is there any WordPress update.

```
wp core check-update --allow-root
```

Update WordPress core only.

```
wp core update --allow-root
```
Upgrade or update WordPress database.
```
wp core update-db --allow-root
```
Check WordPress database.
```
wp db check --allow-root
```


