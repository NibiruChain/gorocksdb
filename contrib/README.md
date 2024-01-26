# Commands to build librocksdb

## Build librocksdb.a

```bash
docker build -t librocksdb:latest .

docker run -it --rm -v $(pwd):/out librocksdb:latest

# inside docker container
cp /rocksdb/librocksdb.a /out
```

## Tar librocksdb.a

```bash
tar -czvf librocksdb_8.9.1_linux_arm64.tar.gz librocksdb.a
```

## Build Mac Universal Static Library

```bash
lipo -create librocksdb_darwin_amd64.a librocksdb_darwin_arm64.a -output librocksdb.a
```
