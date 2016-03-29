Sometimes you do `yum update` and system will show many duplicates error/warning. Just do these.

```bash
yum-complete-transaction
package-cleanup --problems
package-cleanup --dupes
package-cleanup --cleandupes
rpm -Va --nofiles --nodigest

yum clean all
rpm --rebuilddb
yum update
```
