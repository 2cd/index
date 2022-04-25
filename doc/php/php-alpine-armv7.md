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
tag = ["alpine", "2022-04-25", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false
syntax_version = "0.0.0-alpha.3"

[file]
name = "php-musl_armhf_2022-04-25_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "e994b2d1ade7317cfda7ffae684f33fb99e4fddf7df5482f05ad539cbc275517"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "75M"
tar_bytes = 78418432

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "23M"
zstd_bytes = 23676891

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220411"
previous_tag = "2022-04-11"
previous_file = "php-musl_armhf_2022-04-11_11-04-rootfs.tar.zst"
previous_sha256 = "478a88eb656b5058c99673afc9b627e372f550632847d5f7c954b2ab375e95ac"

current_version = "latest02"
current_date = "20220425"
old_file = "php-musl_armhf_2022-03-28_11-03-rootfs.tar.zst"
old_sha256 = "e33eb772acc8c69d669c3d969528e9efee38a43fe026e91c871e16c00c8f0d9c"
# edition 2021
# DISTRO_NAME=php_armhf
# ROOTFS_FILE=php-musl_armhf_2022-04-25_12-04-rootfs.tar.zst
# SHA256SUM=e994b2d1ade7317cfda7ffae684f33fb99e4fddf7df5482f05ad539cbc275517
# BUILD_DATE=20220425
# BUILD_TAG=2022-04-25
# STATUS=completed
# VERSION=latest02
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-25
begin = 2022-04-25 12:02:34.439943519+00:00
start-sync_0 = 12:03:29
start-zstd = 12:03:42
start-sync_1 = 12:04:15
end-sync_1 = 12:04:25
end = 2022-04-25 12:04:25.673242013+00:00

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
PHP 8.1.5 (cli) (built: Apr 19 2022 01:59:24) (NTS)
Copyright (c) The PHP Group
Zend Engine v4.1.5, Copyright (c) Zend Technologies
'''

[other]
phpize_deps = 'autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c'
php_extra_configure_args = '--enable-embed'
php_cflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_cppflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_ldflags = '-Wl,-O1 -pie'
gpg_keys = '528995BFEDFBA7191D46839EF9BA0ADA31CBD89E 39B641343D8C104B2B146DC3F9C39DC0B9698544 F1F692238FBC1666E5A5CCD4199F9DFEF6FFBAFD'
php_url = 'https://www.php.net/distributions/php-8.1.5.tar.xz'
php_src_url = 'https://www.php.net/distributions/php-8.1.5.tar.xz.asc'
```
