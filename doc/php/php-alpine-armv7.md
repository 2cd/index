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
tag = ["alpine", "2022-07-18", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "php-musl_armhf_2022-07-18_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "299378c0a65ea990c71935d6fe7c7b01e08833804a82ebda7606e5df8d921c5b"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "75M"
tar_bytes = 78406144

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "23M"
zstd_bytes = 23672883

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220704"
previous_tag = "2022-07-04"
previous_file = "php-musl_armhf_2022-07-04_12-04-rootfs.tar.zst"
previous_sha256 = "de85e97c7703846b9d31bf3f861e355a5910b1d529c8e0d43a497509fddd57f0"

current_version = "latest02"
current_date = "20220718"
old_file = "php-musl_armhf_2022-06-20_12-04-rootfs.tar.zst"
old_sha256 = "13cf205853925b816a96d5feffad1d9ccefa7cea3a1a5ff1a52815e968f54a6e"
# edition 2021
# DISTRO_NAME=php_armhf
# ROOTFS_FILE=php-musl_armhf_2022-07-18_12-04-rootfs.tar.zst
# SHA256SUM=299378c0a65ea990c71935d6fe7c7b01e08833804a82ebda7606e5df8d921c5b
# BUILD_DATE=20220718
# BUILD_TAG=2022-07-18
# STATUS=completed
# VERSION=latest02
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-18
begin = 2022-07-18 12:02:30.875766712+00:00
start-sync_0 = 12:03:30
start-zstd = 12:03:40
start-sync_1 = 12:04:08
end-sync_1 = 12:04:16
end = 2022-07-18 12:04:16.820640168+00:00

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
PHP 8.1.8 (cli) (built: Jul  7 2022 22:59:52) (NTS)
Copyright (c) The PHP Group
Zend Engine v4.1.8, Copyright (c) Zend Technologies
'''

[other]
phpize_deps = 'autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c'
php_extra_configure_args = '--enable-embed'
php_cflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_cppflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_ldflags = '-Wl,-O1 -pie'
gpg_keys = '528995BFEDFBA7191D46839EF9BA0ADA31CBD89E 39B641343D8C104B2B146DC3F9C39DC0B9698544 F1F692238FBC1666E5A5CCD4199F9DFEF6FFBAFD'
php_url = 'https://www.php.net/distributions/php-8.1.8.tar.xz'
php_src_url = 'https://www.php.net/distributions/php-8.1.8.tar.xz.asc'
```
