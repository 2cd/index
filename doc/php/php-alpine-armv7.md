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
tag = ["alpine", "2022-10-24", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "php-musl_armhf_2022-10-24_18-15.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ace4e44c47d154fc9bb47ac8a9987747b1d437788339f6742adb5ea2fefd88b4"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "75M"
tar_bytes = 78462464

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "23M"
zstd_bytes = 23756692

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221010"
previous_tag = "2022-10-10"
previous_file = "php-musl_armhf_2022-10-10_12-04-rootfs.tar.zst"
previous_sha256 = "d603eeca8ca0b1dbcf1847f64ccebd5cb2060a93e91bfc3130ad520a95df7a8b"

current_version = "latest01"
current_date = "20221024"
old_file = "php-musl_armhf_2022-09-26_12-05-rootfs.tar.zst"
old_sha256 = "d72369688c096ea454416bf03b69c32721dbf0c8d9030765502876b8e6e78f98"
# edition 2021
# DISTRO_NAME=php_armhf
# ROOTFS_FILE=php-musl_armhf_2022-10-24_18-15-rootfs.tar.zst
# SHA256SUM=ace4e44c47d154fc9bb47ac8a9987747b1d437788339f6742adb5ea2fefd88b4
# BUILD_DATE=20221024
# BUILD_TAG=2022-10-24
# STATUS=completed
# VERSION=latest01
# END_TIME=18:15

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-24
begin = 2022-10-24 18:13:42.388676847+00:00
start-sync_0 = 18:14:20
start-zstd = 18:14:33
start-sync_1 = 18:15:09
end-sync_1 = 18:15:19
end = 2022-10-24 18:15:19.709340512+00:00

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
current = true
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = true
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
ldd = 'musl libc (armhf) Version 1.2.3'
php = '''
PHP 8.1.11 (cli) (built: Oct  7 2022 23:54:36) (NTS)
Copyright (c) The PHP Group
Zend Engine v4.1.11, Copyright (c) Zend Technologies
'''

[other]
phpize_deps = 'autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c'
php_extra_configure_args = '--enable-embed'
php_cflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_cppflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_ldflags = '-Wl,-O1 -pie'
gpg_keys = '528995BFEDFBA7191D46839EF9BA0ADA31CBD89E 39B641343D8C104B2B146DC3F9C39DC0B9698544 F1F692238FBC1666E5A5CCD4199F9DFEF6FFBAFD'
php_url = 'https://www.php.net/distributions/php-8.1.11.tar.xz'
php_src_url = 'https://www.php.net/distributions/php-8.1.11.tar.xz.asc'
```
