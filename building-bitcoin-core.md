# Building Bitcoin Core
This is all done in bitcoin's root directory and assuming the [dependencies](https://github.com/bitcoin/bitcoin/blob/master/doc/build-osx.md) are installed.

## Using Berkely DB 4.8
How to build Berkeley DB 4.8:
```shell
./contrib/install_db4.sh .
```
This will give the following output:
> When compiling bitcoind, run `./configure` in the following way:
>
>  export BDB_PREFIX='/Users/matthewcruz/Desktop/GitHub/forked-bitcoin/bitcoin/db4' \
>  ./configure BDB_LIBS="-L${BDB_PREFIX}/lib -ldb_cxx-4.8" BDB_CFLAGS="-I${BDB_PREFIX}/include" ...

## Build Bitcoin Core
Optional `./configure` arguments:
* Debug enabled `--enable-debug`
* Disable the GUI with `--without-gui`
* Disable the wallet, to only run a P2P node `--disable-wallet`
Run the following commands to build:
```shell
./autogen.sh
export BDB_PREFIX=''
./configure BDB_LIBS="-L${BDB_PREFIX}/lib -ldb_cxx-4.8" BDB_CFLAGS="-I${BDB_PREFIX}/include"
make
```
After building, the next step is to [test](testing-bitcoin-core.md).
