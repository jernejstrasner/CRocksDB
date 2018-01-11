# CRocksDB

A thin wrapper around the [RocksDB](https://github.com/facebook/rocksdb/) library for the Swift Package Manager.

## Install RocksDB using Homebrew (Mac)

```
brew install rocksdb
```

## rocksdb.pc

SPM uses the `pkg-config` tool to locate libraries on the system. RocksDB does not ship with a rocksdb.pc file as of writing this so you will likely have to create one yourself. Create a file at `/usr/local/lib/pkgconfig/rocksdb.pc` with the following contents:

```
prefix=/usr/local/Cellar/rocksdb/5.9.2_1 # Replace this with the path to your library (brew ls rocksdb)
exec_prefix=${prefix}
libdir=${exec_prefix}/lib
includedir=${prefix}/include
libname=rocksdb

Name: rocksdb
Description: RocksDB
Version: 5.9.2
Libs: -L${libdir} -l${libname}
Cflags: -I${includedir}
```
