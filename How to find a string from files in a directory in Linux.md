Try to use this.

~~~
grep -rl "string" /path
~~~

where

* `-r` (or --recursive) option is used to traverse also all sub-directories of /path, whereas
* `-l` (or --files-with-matches) option is used to only print filenames of matching files, and not the matching lines (this could also improve the speed, given that grep stop reading a file at first match with this option).
