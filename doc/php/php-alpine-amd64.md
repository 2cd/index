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
tag = ["alpine", "2022-02-14", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "php-musl_amd64_2022-02-14_12-03.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "972b53b1118252902e437c833f8b6ab0eaf3e1ea27d5f3b0f97f3292eb20d0fb"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "100M"
tar_bytes = 104358400

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "30M"
zstd_bytes = 30595310

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220131"
previous_tag = "2022-01-31"
previous_file = "php-musl_amd64_2022-01-31_12-03-rootfs.tar.zst"
previous_sha256 = "5652076e2d4a62b798d72b44e7422d4fa40377c1ad02c683c0ceae27d5f8a5bc"

current_version = "latest01"
current_date = "20220214"
old_file = "php-musl_amd64_2022-01-17_12-03-rootfs.tar.zst"
old_sha256 = "0a931227d4907df269526f323c8f4d8d30a7105e2e2d23d5f90be2e0731a0d9a"
# edition 2021
# DISTRO_NAME=php_amd64
# ROOTFS_FILE=php-musl_amd64_2022-02-14_12-03-rootfs.tar.zst
# SHA256SUM=972b53b1118252902e437c833f8b6ab0eaf3e1ea27d5f3b0f97f3292eb20d0fb
# BUILD_DATE=20220214
# BUILD_TAG=2022-02-14
# STATUS=completed
# VERSION=latest01
# END_TIME=12:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-14
begin = 2022-02-14 12:02:30.838198527+00:00
start-sync_0 = 12:03:11
start-zstd = 12:03:23
start-sync_1 = 12:03:34
end-sync_1 = 12:03:45
end = 2022-02-14 12:03:45.980978144+00:00

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
ldd = 'musl libc (x86_64) Version 1.2.2'
php = '''
PHP 8.1.2 (cli) (built: Jan 21 2022 21:38:22) (NTS)
Copyright (c) The PHP Group
Zend Engine v4.1.2, Copyright (c) Zend Technologies
'''

[other]
phpize_deps = 'autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c'
php_extra_configure_args = '--enable-embed'
php_cflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_cppflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_ldflags = '-Wl,-O1 -pie'
gpg_keys = '528995BFEDFBA7191D46839EF9BA0ADA31CBD89E 39B641343D8C104B2B146DC3F9C39DC0B9698544 F1F692238FBC1666E5A5CCD4199F9DFEF6FFBAFD'
php_url = 'https://www.php.net/distributions/php-8.1.2.tar.xz'
php_src_url = 'https://www.php.net/distributions/php-8.1.2.tar.xz.asc'
```
