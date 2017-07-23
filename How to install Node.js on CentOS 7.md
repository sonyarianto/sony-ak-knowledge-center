Scenario 1:

Make sure to do this.

```
sudo yum install epel-release
```

After that do this.

```
sudo yum install nodejs
```

Scenario 2:

Install from source. Go to https://nodejs.org/en/download/

Download the source code (tar.gz) format, using `wget` maybe.

Run this.

```
tar xzvf node-v* && cd node-v*
```

Make sure you have `gcc`, if not sure just do this.

```
yum install gcc gcc-c++
```

then do this.
```
./configure
make
```
and then do this.

```
make install
```

