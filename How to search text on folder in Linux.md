Look on current folder and its sub folder

```
find . -type f -exec grep -H 'search text here' {} \;
```
or look at example below.
```
grep -rnw '/path/to/somewhere/' -e 'pattern'
```
