Create the copy script like below:

~~~bash
#!/usr/bin/env bash

dest="/this/is/your/target/folder/";

while read path; do
    target=$path;
    cp "$path" "$dest"/"$target";
done
~~~

Save it to `mass_copy.sh` and `chmod` it to `777`.

Now suppose you have 5 files to copy on file `files_to_be_copied`

~~~
/source/folder/of/files/1.txt
/source/folder/of/files/2.txt
/source/folder/of/files/3.txt
/source/folder/of/files/4.txt
/source/folder/of/files/5.txt
~~~

Run the `mass_copy` script like below:

~~~bash
./mass_copy.sh < files_to_be_copied
~~~

Now all of your files on 'files_to_be_copied' will be coppied to folder `/this/is/your/target/folder/`. If the those files already exists on target then files will be overwritten.
