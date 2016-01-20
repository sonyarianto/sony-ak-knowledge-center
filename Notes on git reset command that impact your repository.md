If you do
~~~
git reset --hard xxxxx
~~~
It will make your local code and local history be just like it was at that commit. But then if you wanted to push this to someone else who has the new history, it would fail.

If you do
~~~
git reset --soft xxxxx
~~~
It will make your local files changed to be like they were then, but leave your history etc. the same.

So what exactly do you want to do with this reset?
