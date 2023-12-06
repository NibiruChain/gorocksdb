FROM ubuntu:22.04

ENV PORTABLE=1
ARG ROCKSDB_VERSION=v8.5.3

WORKDIR /

RUN apt-get update && \
  apt-get install -y \
  git make build-essential libgflags-dev libsnappy-dev zlib1g-dev libbz2-dev liblz4-dev libzstd-dev && \
  rm -rf /var/lib/apt/lists/*

RUN git clone https://github.com/facebook/rocksdb.git && \
  cd rocksdb && \
  git checkout $ROCKSDB_VERSION && \
  make -j4 static_lib