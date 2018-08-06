First see all installed plugins.

```
wp plugin list --allow-root
```

Example results like below.

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

To update then do this.

```
wp plugin update all-in-one-seo-pack --allow-root
```

Now see the WordPress version with this.

```
wp core version --allow-root
```

It will display like below.
```
4.9.7
```

Check is there any update with this command.

```
wp core check-update --allow-root
```

To update WordPress do this.

```
wp core update --allow-root
```

Do WordPress DB check
```
wp db check --allow-root
```

Do upgrade or update WP database
```
wp core update-db --allow-root
```
