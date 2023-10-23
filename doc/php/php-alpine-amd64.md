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
tag = ["alpine", "2023-10-23", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "php-musl_amd64_2023-10-23_12-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "e5eee15e3400abcc76314fa15f6ddd70cb5ea852a1d21bfd7a1a000a62cb021f"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "104M"
tar_bytes = 108282880

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "26M"
zstd_bytes = 26570112

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231009"
previous_tag = "2023-10-09"
previous_file = "php-musl_amd64_2023-10-09_12-04-rootfs.tar.zst"
previous_sha256 = "4da2273108adc3e9a3427eeb70ae26bcb56f25075d3bb09356abc023e92381e7"

current_version = "latest01"
current_date = "20231023"
old_file = "php-musl_amd64_2023-09-25_12-05-rootfs.tar.zst"
old_sha256 = "1194c72907e6ac97f9a88e40d12024a693275b1e32ef31df963b5d0adf97c5b1"
# edition 2021
# DISTRO_NAME=php_amd64
# ROOTFS_FILE=php-musl_amd64_2023-10-23_12-05-rootfs.tar.zst
# SHA256SUM=e5eee15e3400abcc76314fa15f6ddd70cb5ea852a1d21bfd7a1a000a62cb021f
# BUILD_DATE=20231023
# BUILD_TAG=2023-10-23
# STATUS=completed
# VERSION=latest01
# END_TIME=12:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-23
begin = 2023-10-23 12:02:38.861109391+00:00
start-sync_0 = 12:04:30
start-zstd = 12:04:39
start-sync_1 = 12:05:22
end-sync_1 = 12:05:32
end = 2023-10-23 12:05:32.390861097+00:00

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
ldd = 'musl libc (x86_64) Version 1.2.4'
php = '''
PHP 8.2.11 (cli) (built: Oct 21 2023 04:41:10) (NTS)
Copyright (c) The PHP Group
Zend Engine v4.2.11, Copyright (c) Zend Technologies
'''

[other]
phpize_deps = 'autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c'
php_extra_configure_args = '--enable-embed'
php_cflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_cppflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_ldflags = '-Wl,-O1 -pie'
gpg_keys = '39B641343D8C104B2B146DC3F9C39DC0B9698544 E60913E4DF209907D8E30D96659A97C9CF2A795A 1198C0117593497A5EC5C199286AF1F9897469DC'
php_url = 'https://www.php.net/distributions/php-8.2.11.tar.xz'
php_src_url = 'https://www.php.net/distributions/php-8.2.11.tar.xz.asc'
```
