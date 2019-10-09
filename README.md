# get

Installing a specific version to `~/bin`:

```sh
curl -sL https://raw.githubusercontent.com/variantdev/get/master/get | VERSION=v0.35.1 INSTALL_TO=~/bin bash version
PATH=$PATH:~/bin

$ variant version
0.35.1
```

Run the latest variant binary

```sh
curl -sL https://raw.githubusercontent.com/variantdev/get/master/get | bash
```

Or, if you want to lock an specific version:

```sh
curl -sL https://raw.githubusercontent.com/variantdev/get/master/get | VERSION=v0.35.1 bash
```

Run any command immediately without installing:

```sh
curl -sL https://raw.githubusercontent.com/variantdev/get/master/get | bash version
```

## Docker

The same script works even within a docker container:

### Alpine

```
$ docker run -it --rm alpine:3.9 sh
/ # apk add --update --no-cache curl
fetch http://dl-cdn.alpinelinux.org/alpine/v3.9/main/x86_64/APKINDEX.tar.gz
fetch http://dl-cdn.alpinelinux.org/alpine/v3.9/community/x86_64/APKINDEX.tar.gz
(1/5) Installing ca-certificates (20190108-r0)
(2/5) Installing nghttp2-libs (1.35.1-r1)
(3/5) Installing libssh2 (1.8.2-r0)
(4/5) Installing libcurl (7.64.0-r3)
(5/5) Installing curl (7.64.0-r3)
Executing busybox-1.29.3-r10.trigger
Executing ca-certificates-20190108-r0.trigger
OK: 7 MiB in 19 packages
/ # curl -sL https://raw.githubusercontent.com/variantdev/get/master/get | INSTALL_TO=/usr/local/bin sh
Installing variant to /usr/local/bin...
Done!
/ # /usr/local/bin/variant version
0.35.1
```
