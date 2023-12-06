```bash
docker build -t librocksdb:latest --platform=linux/amd64,linux/arm64 .

docker run -it --rm -v $(pwd):/out librocksdb:latest

# inside docker container
cp /rocksdb/librocksdb.a /out
```
