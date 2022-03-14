# php-alpine-armv7

## How to run it?

```sh
docker run \
    -it \
    --name php-alpine-armv7 \
    cake233/php-alpine-armv7
```

## How to exec shell?

```sh
docker exec -it php-alpine-armv7 bash
```

## php-alpine-armv7.toml

```toml
[main]
name = "php"
tag = ["alpine", "2022-03-14", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "php-musl_armhf_2022-03-14_12-04.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "8abc9db060bd19f40f626e6a9d64159ee542ff661d0d95967295d7b8987281c0"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "75M"
tar_bytes = 78410752

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "23M"
zstd_bytes = 23671599

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220301"
previous_tag = "2022-03-01"
previous_file = "php-musl_armhf_2022-03-01_18-54-rootfs.tar.zst"
previous_sha256 = "f553a74395f319df9220c75803c88d4a4e33d02c4d83425e1dfbcc4feabdce4d"

current_version = "latest02"
current_date = "20220314"
old_file = "php-musl_armhf_2022-02-14_12-03-rootfs.tar.zst"
old_sha256 = "ccc8ddaf77a4a1416cd92c996fc12fcde69b316027badcc2d1a19ae1e457f7ff"
# edition 2021
# DISTRO_NAME=php_armhf
# ROOTFS_FILE=php-musl_armhf_2022-03-14_12-04-rootfs.tar.zst
# SHA256SUM=8abc9db060bd19f40f626e6a9d64159ee542ff661d0d95967295d7b8987281c0
# BUILD_DATE=20220314
# BUILD_TAG=2022-03-14
# STATUS=completed
# VERSION=latest02
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-14
begin = 2022-03-14 12:02:32.403504494+00:00
start-sync_0 = 12:03:20
start-zstd = 12:03:29
start-sync_1 = 12:03:57
end-sync_1 = 12:04:06
end = 2022-03-14 12:04:06.111101057+00:00

[server]
repo = "cake233/php-alpine-armv7"

[server.node1]
name = "cn"
current = false
previous = false
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
previous = true
in_sync = false
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "C.UTF-8"
PHP_INI_DIR = '/usr/local/etc/php'

[version]
ldd = 'musl libc (armhf) Version 1.2.2'
php = '''
PHP 8.1.3 (cli) (built: Mar 11 2022 02:40:51) (NTS)
Copyright (c) The PHP Group
Zend Engine v4.1.3, Copyright (c) Zend Technologies
'''

[other]
phpize_deps = 'autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c'
php_extra_configure_args = '--enable-embed'
php_cflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_cppflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_ldflags = '-Wl,-O1 -pie'
gpg_keys = '528995BFEDFBA7191D46839EF9BA0ADA31CBD89E 39B641343D8C104B2B146DC3F9C39DC0B9698544 F1F692238FBC1666E5A5CCD4199F9DFEF6FFBAFD'
php_url = 'https://www.php.net/distributions/php-8.1.3.tar.xz'
php_src_url = 'https://www.php.net/distributions/php-8.1.3.tar.xz.asc'
```
