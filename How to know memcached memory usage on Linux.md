```bash
echo "stats" | nc -w 1 <host> <port> | awk '$2 == "bytes" { print $2" "$3 }'
```
so the sample is below.
```bash
echo "stats" | nc -w 1 localhost 11211 | awk '$2 == "bytes" { print $2" "$3 }'
```
it will display like below
```
bytes 550721
```
