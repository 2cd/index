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
tag = ["alpine", "2022-08-01", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "php-musl_amd64_2022-08-01_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "2c80708ece66f52f35bbcb699196a89241b6cf524bb5281e77426b736bd55c55"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "101M"
tar_bytes = 105428480

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "25M"
zstd_bytes = 25287680

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220704"
previous_tag = "2022-07-04"
previous_file = "php-musl_amd64_2022-07-04_12-03-rootfs.tar.zst"
previous_sha256 = "c76a58bc4b955402c2adc07eaadd5926b9d92639c3b8bb9099f9a15db6a70f9d"

current_version = "latest02"
current_date = "20220801"
old_file = "php-musl_amd64_2022-06-20_12-04-rootfs.tar.zst"
old_sha256 = "a55fabc261441ebecd9c081b0ea8f2feadd5330438c3dbc12c948d3bb0bd8109"
# edition 2021
# DISTRO_NAME=php_amd64
# ROOTFS_FILE=php-musl_amd64_2022-08-01_12-04-rootfs.tar.zst
# SHA256SUM=2c80708ece66f52f35bbcb699196a89241b6cf524bb5281e77426b736bd55c55
# BUILD_DATE=20220801
# BUILD_TAG=2022-08-01
# STATUS=completed
# VERSION=latest02
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-01
begin = 2022-08-01 12:02:36.317974352+00:00
start-sync_0 = 12:03:40
start-zstd = 12:03:50
start-sync_1 = 12:04:31
end-sync_1 = 12:04:40
end = 2022-08-01 12:04:40.202543809+00:00

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
ldd = 'musl libc (x86_64) Version 1.2.3'
php = '''
PHP 8.1.8 (cli) (built: Jul 19 2022 00:44:15) (NTS)
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
