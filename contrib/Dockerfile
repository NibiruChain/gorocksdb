FROM debian:bullseye-slim

ENV PORTABLE=1
ARG ROCKSDB_VERSION=v8.9.1

WORKDIR /

RUN apt-get update && \
  apt-get install --no-install-recommends -y \
  git ca-certificates build-essential liblz4-dev libsnappy-dev zlib1g-dev libbz2-dev libzstd-dev && \
  rm -rf /var/lib/apt/lists/*

RUN git clone --depth 1 --branch $ROCKSDB_VERSION https://github.com/facebook/rocksdb.git && \
  cd rocksdb && \
  PORTABLE=1 make PORTABLE=1 -j4 static_lib