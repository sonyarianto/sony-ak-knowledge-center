Suppose you have a repository with many commits and one day you just realize that your current code has a bug and you don't know from which commit the bug was introduced.

Solution is:
* Clone your repo to new folder
* Get latest succesfull code commit (which is have no bug with command:
```
git checkout -b new_branch_name xxxx
```

Where `xxxx` is is commit hash.
