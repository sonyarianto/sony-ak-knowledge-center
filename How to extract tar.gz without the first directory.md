Usually I extract `tar.gz` file with this command

```bash
tar -zxvf {file.tar.gz}
```

but actually I don't want it to create the parent directory (or the first directory). Then just type this command.

```bash
tar -zxvf {file.tar.gz} --strip 1
```

That's it and DONE.
