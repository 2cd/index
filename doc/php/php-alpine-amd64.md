# php-alpine-amd64

## How to run it?

```sh
docker run \
    -it \
    --name php-alpine-amd64 \
    cake233/php-alpine-amd64
```

## How to exec shell?

```sh
docker exec -it php-alpine-amd64 bash
```

## php-alpine-amd64.toml

```toml
[main]
name = "php"
tag = ["alpine", "2022-05-09", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "php-musl_amd64_2022-05-09_20-23.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "09e61bd243f7d1d633756338ee68b04acf675499def58fca1b46edddb40be187"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "101M"
tar_bytes = 105505280

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "25M"
zstd_bytes = 25286742

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220425"
previous_tag = "2022-04-25"
previous_file = "php-musl_amd64_2022-04-25_12-03-rootfs.tar.zst"
previous_sha256 = "7363561bd610f7212f38e8361cff06548aab8956ef8000bc243171425b4cf4f3"

current_version = "latest02"
current_date = "20220509"
old_file = "php-musl_amd64_2022-04-11_11-04-rootfs.tar.zst"
old_sha256 = "d6acf178b84e6f5958d07a706fcd2cb9a6ee7e5885b5ef51327a4659ce680472"
# edition 2021
# DISTRO_NAME=php_amd64
# ROOTFS_FILE=php-musl_amd64_2022-05-09_20-23-rootfs.tar.zst
# SHA256SUM=09e61bd243f7d1d633756338ee68b04acf675499def58fca1b46edddb40be187
# BUILD_DATE=20220509
# BUILD_TAG=2022-05-09
# STATUS=completed
# VERSION=latest02
# END_TIME=20:23

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-09
begin = 2022-05-09 20:22:18.403644462+00:00
start-sync_0 = 20:22:37
start-zstd = 20:22:48
start-sync_1 = 20:23:32
end-sync_1 = 20:23:41
end = 2022-05-09 20:23:41.589411937+00:00

[server]
repo = "cake233/php-alpine-amd64"

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
ldd = 'musl libc (x86_64) Version 1.2.2'
php = '''
PHP 8.1.5 (cli) (built: Apr 18 2022 23:48:54) (NTS)
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
