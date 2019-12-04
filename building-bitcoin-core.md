# Building Bitcoin Core
This is all done in bitcoin's base directory.

## Berkely DB 4.8
How to build Berkeley DB 4.8:
```shell
./contrib/install_db4.sh .
```
This will give the following output:
> When compiling bitcoind, run `./configure` in the following way:
>
>  export BDB_PREFIX='/Users/matthewcruz/Desktop/GitHub/forked-bitcoin/bitcoin/db4'
>  ./configure BDB_LIBS="-L${BDB_PREFIX}/lib -ldb_cxx-4.8" BDB_CFLAGS="-I${BDB_PREFIX}/include" ...

## Build Bitcoin Core
Optional `./configure` arguments:
* Disable the GUI with `--without-gui`
* Disable the wallet, to only run a P2P node `--disable-wallet`

```shell
./autogen.sh
./configure BDB_LIBS="-L${BDB_PREFIX}/lib -ldb_cxx-4.8" BDB_CFLAGS="-I${BDB_PREFIX}/include"
make
```
