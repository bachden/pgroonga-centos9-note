#install pgroonga centos9

## install development tools: 
```
yum groupinstall -y "development tools"
```
## install Groonga from source
follow link: https://groonga.org/docs/install/centos.html
## install Pgroonga
follow link: https://pgroonga.github.io/install/source.html
- install msgpack: `yum install -y msgpack-devel`
- install postgresql16-devel: `yum install -y postgresql16-devel`
- use command: `export PKG_CONFIG_PATH=/usr/local/lib/pkgconfig make HAVE_MSGPACK=1`
- incase of error "unknown -no-opaque-pointers...", edit /usr/pgsql-16/lib/pgxs/src/makefiles/../../src/Makefile.global and remove that argument where it found
- incase of create extension error libgroonga.so.0 cannot be loaded, run following command: `ln -fs /usr/local/lib/libgroonga.so.0.0.0 /usr/pgsql-16/lib/libgroonga.so.0`
