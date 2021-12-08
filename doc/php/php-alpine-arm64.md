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
tag = ["alpine", "2021-12-06", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "php-musl_arm64_2021-12-06_20-05.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "45155ad64c7a3f92516ec03bd1cb09d1c8bb32034686d97c065055e8a312f841"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "90M"
tar_bytes = 93881344

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "29M"
zstd_bytes = 30370898

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211129"
previous_tag = "2021-11-29"
previous_file = "php-musl_arm64_2021-11-29_01-03-rootfs.tar.zst"

current_version = "latest01"
current_date = "20211206"
old_file = "php_arm64+alpine-2021_11-01-rootfs.tar.zst"
# edition 2021
# DISTRO_NAME=php_arm64
# ROOTFS_FILE=php-musl_arm64_2021-12-06_20-05-rootfs.tar.zst
# BUILD_DATE=20211206
# BUILD_TAG=2021-12-06
# STATUS=completed
# VERSION=latest01
# END_TIME=20:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-06
begin = 2021-12-06 20:04:26.818002469+00:00
start-sync_0 = 20:05:01
start-zstd = 20:05:12
start-sync_1 = 20:05:23
end-sync_1 = 20:05:30
end = 2021-12-06 20:05:30.422123315+00:00

[server]
repo = "cake233/php-alpine-arm64"

[server.node1]
name = "cn"
current = false
previous = true
in_sync = false
split = false

[server.node2]
name = "us"
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "global"
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
php = '''
PHP 8.1.0 (cli) (built: Nov 30 2021 02:53:30) (NTS)
Copyright (c) The PHP Group
Zend Engine v4.1.0, Copyright (c) Zend Technologies
'''

[other]
phpize_deps = 'autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c'
php_extra_configure_args = '--enable-embed'
php_cflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_cppflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_ldflags = '-Wl,-O1 -pie'
gpg_keys = '528995BFEDFBA7191D46839EF9BA0ADA31CBD89E 39B641343D8C104B2B146DC3F9C39DC0B9698544 F1F692238FBC1666E5A5CCD4199F9DFEF6FFBAFD'
php_url = 'https://www.php.net/distributions/php-8.1.0.tar.xz'
php_src_url = 'https://www.php.net/distributions/php-8.1.0.tar.xz.asc'
```
