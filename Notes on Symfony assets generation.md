There are several options.

* Hard copy
```
php app/console assets:install // it will copy Resources/public on any bundle to web/ folder
```

```
php app/console assets:install web // similar to above
```

* Symbolic links
```
php app/console assets:install web --symlink // it will create symbolic links from Resources/public on any bundle to web/ folder
```

```
php app/console assets:install --symlink // similar to above
```
