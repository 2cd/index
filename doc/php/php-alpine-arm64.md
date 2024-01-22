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
tag = ["alpine", "2024-01-22", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "php-musl_arm64_2024-01-22_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "029c853ca8f70459fa14909d09fade84cda7a7d8e9e089a53efa7e6fc2c27b4c"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "108M"
tar_bytes = 112641536

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "27M"
zstd_bytes = 27395538

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231023"
previous_tag = "2023-10-23"
previous_file = "php-musl_arm64_2023-10-23_12-05-rootfs.tar.zst"
previous_sha256 = "7625f3c5bf5d73c1d833e95ad09717c603ea80c536b41bab9cd68c7480d3e6d9"

current_version = "latest02"
current_date = "20240122"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=php_arm64
# ROOTFS_FILE=php-musl_arm64_2024-01-22_12-04-rootfs.tar.zst
# SHA256SUM=029c853ca8f70459fa14909d09fade84cda7a7d8e9e089a53efa7e6fc2c27b4c
# BUILD_DATE=20240122
# BUILD_TAG=2024-01-22
# STATUS=completed
# VERSION=latest02
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-01-22
begin = 2024-01-22 12:02:32.409180255+00:00
start-sync_0 = 12:04:05
start-zstd = 12:04:12
start-sync_1 = 12:04:52
end-sync_1 = 12:04:58
end = 2024-01-22 12:04:58.532922446+00:00

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
ldd = 'musl libc (aarch64) Version 1.2.4_git20230717'
php = '''
PHP 8.3.2 (cli) (built: Jan 19 2024 23:24:10) (NTS)
Copyright (c) The PHP Group
Zend Engine v4.3.2, Copyright (c) Zend Technologies
'''

[other]
phpize_deps = 'autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c'
php_extra_configure_args = '--enable-embed'
php_cflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_cppflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_ldflags = '-Wl,-O1 -pie'
gpg_keys = '1198C0117593497A5EC5C199286AF1F9897469DC C28D937575603EB4ABB725861C0779DC5C0A9DE4 AFD8691FDAEDF03BDF6E460563F15A9B715376CA'
php_url = 'https://www.php.net/distributions/php-8.3.2.tar.xz'
php_src_url = 'https://www.php.net/distributions/php-8.3.2.tar.xz.asc'
```
