Suppose in `master` branch you have this situation.

```
git log --no-merges
```

Result are
```
55555
44444
33333
22222
11111
```

You want to create new branch that skip a commit.
```
git branch <branch_name> <commit_sha>
```

Let say I want to create branch called `anu` start on commit SHA `33333` and skip commit `44444`

```
git branch anu 33333
```
then
```
git checkout anu
```
check first with
```
git log --no-merge
```
the last commit on branch `anu` should be `33333` then skip commit `44444` by cherry-picking any commit you want to `anu` branch from `master`.

```
git cherry-pick 55555
```
now on branch `anu` if you do `git log --no-merges` the result will be like this.
```
55555
33333
22222
11111
```

Now you can push that to a branch on GitHub such as like below
```
git push -u origin anu
```
