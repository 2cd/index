# php-alpine-arm64

## How to run it?

```sh
docker run \
    -it \
    --name php-alpine-arm64 \
    cake233/php-alpine-arm64
```

## How to exec shell?

```sh
docker exec -it php-alpine-arm64 bash
```

## php-alpine-arm64.toml

```toml
[main]
name = "php"
tag = ["alpine", "2022-06-20", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "php-musl_arm64_2022-06-20_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "0edc21dcac09209ab67e13074adce465ede3279fccb0663da44c401e55c41e19"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "91M"
tar_bytes = 94929408

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "25M"
zstd_bytes = 25255670

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220606"
previous_tag = "2022-06-06"
previous_file = "php-musl_arm64_2022-06-06_12-04-rootfs.tar.zst"
previous_sha256 = "1807b7115e2f68c101203b100caa4128164b46c3f3da90bca7394e457273cfed"

current_version = "latest01"
current_date = "20220620"
old_file = "php-musl_arm64_2022-05-23_12-04-rootfs.tar.zst"
old_sha256 = "a267552067436c090c547d681db498d0ee80f4a453f8b5283a82b910a5f10b55"
# edition 2021
# DISTRO_NAME=php_arm64
# ROOTFS_FILE=php-musl_arm64_2022-06-20_12-04-rootfs.tar.zst
# SHA256SUM=0edc21dcac09209ab67e13074adce465ede3279fccb0663da44c401e55c41e19
# BUILD_DATE=20220620
# BUILD_TAG=2022-06-20
# STATUS=completed
# VERSION=latest01
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-20
begin = 2022-06-20 12:02:31.416866524+00:00
start-sync_0 = 12:03:22
start-zstd = 12:03:28
start-sync_1 = 12:04:12
end-sync_1 = 12:04:19
end = 2022-06-20 12:04:20.000217529+00:00

[server]
repo = "cake233/php-alpine-arm64"

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
ldd = 'musl libc (aarch64) Version 1.2.3'
php = '''
PHP 8.1.7 (cli) (built: Jun  9 2022 23:22:59) (NTS)
Copyright (c) The PHP Group
Zend Engine v4.1.7, Copyright (c) Zend Technologies
'''

[other]
phpize_deps = 'autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c'
php_extra_configure_args = '--enable-embed'
php_cflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_cppflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_ldflags = '-Wl,-O1 -pie'
gpg_keys = '528995BFEDFBA7191D46839EF9BA0ADA31CBD89E 39B641343D8C104B2B146DC3F9C39DC0B9698544 F1F692238FBC1666E5A5CCD4199F9DFEF6FFBAFD'
php_url = 'https://www.php.net/distributions/php-8.1.7.tar.xz'
php_src_url = 'https://www.php.net/distributions/php-8.1.7.tar.xz.asc'
```
