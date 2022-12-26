## Step 1
get postgres source code from github: https://github.com/postgres/postgres.git

<br/>

## Step 2
build from source  
```shell
cd path_to_your_postgres_folder

./configure --prefix=$HOME/dev/db/pg_latest        \
	--enable-cassert --enable-debug              \
	CFLAGS="-ggdb -O0 -fno-omit-frame-pointer"   \
	CPPFLAGS="-g -O0"

make && make install
```

<br/>

## Step3
init postgres db
``` shell
cd $HOME/dev/db/pg_latest
bin/initdb -D ./pgdata -E UNICODE --locale=C
```

<br/>

## Step4
start/stop db
```
cd $HOME/dev/db/pg_latest

# start db
bin/pg_ctl -D ./pg_data start

# stop db
bin/pg_ctl -D ./pg_data stop

```