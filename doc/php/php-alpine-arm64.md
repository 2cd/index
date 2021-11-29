# php-alpine-arm64

## How to run it?

```shell
docker run \
    -it \
    --name php-alpine-arm64 \
    cake233/php-alpine-arm64
```

## How to exec shell?

```shell
    docker exec -it php-alpine-arm64 bash
```

## php-alpine-arm64.toml

```toml
[main]
name = "php"
tag = ["alpine", "2021-11-29", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "php-musl_arm64_2021-11-29_01-03.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "b4d0b4ad31fc99e2a5eb8d951590621846e9ef6903b7211e4d3069434e092b52"

# zstd: [1-22]
zstd-level = 13

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "86M"
tar_bytes = 89687040

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "30M"
zstd_bytes = 30730199

[compatibility]
compatible_mode = true

last_version = "latest01"

# The value is &str, not int
last_date = "20211101"
last_tag = ""
last_file = "php_arm64+alpine-2021_11-01-rootfs.tar.zst"

current_version = "latest02"
current_date = "20211129"
# edition 2021
# DISTRO_NAME=php_arm64
# ROOTFS_FILE=php-musl_arm64_2021-11-29_01-03.tar.zst
# BUILD_DATE=20211129
# BUILD_TAG=2021-11-29
# STATUS=completed
# VERSION=latest02
# END_TIME=01:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-11-29
begin = 2021-11-29 01:02:44.182103206+00:00
start-sync_0 = 01:03:15
start-zstd = 01:03:22
start-sync_1 = 01:03:26
end-sync_1 = 01:03:33
end = 2021-11-29 01:03:33.816100263+00:00

[server]
repo = "cake233/php-alpine-arm64"

[server.node1]
name = "cn"
current = false
last = true
split = false

[server.node2]
name = "us"
current = false
last = true
split = false
part = 12

[server.node3]
name = "global"
current = false
last = true
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "C.UTF-8"
PHP_INI_DIR = '/usr/local/etc/php'

[version]
php = '''
PHP 8.0.13 (cli) (built: Nov 19 2021 22:15:11) ( NTS )
Copyright (c) The PHP Group
Zend Engine v4.0.13, Copyright (c) Zend Technologies
'''

[other]
phpize_deps = 'autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c'
php_extra_configure_args = '--enable-embed'
php_cflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_cppflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_ldflags = '-Wl,-O1 -pie'
gpg_keys = '1729F83938DA44E27BA0F4D3DBDB397470D12172 BFDDD28642824F8118EF77909B67A5C12229118F'
php_url = 'https://www.php.net/distributions/php-8.0.13.tar.xz'
php_src_url = 'https://www.php.net/distributions/php-8.0.13.tar.xz.asc'
```
