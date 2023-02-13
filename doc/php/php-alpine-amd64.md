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
tag = ["alpine", "2023-02-13", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "php-musl_amd64_2023-02-13_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "e3a857e4ed26a07bdb7b51f3fd9f9f85f99906381b94fe0dd3deeb9ca9120410"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "104M"
tar_bytes = 108797440

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "26M"
zstd_bytes = 26527421

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230130"
previous_tag = "2023-01-30"
previous_file = "php-musl_amd64_2023-01-30_12-04-rootfs.tar.zst"
previous_sha256 = "6cde560b46ee92d3d9826b4c67a9b826485e62cfcd9a6673cc7eddca5afcea5a"

current_version = "latest01"
current_date = "20230213"
old_file = "php-musl_amd64_2023-01-16_12-04-rootfs.tar.zst"
old_sha256 = "47b47a18e40d5fea7df41842cb3927b3bd85c147ce658fe42a60f68f70d967b5"
# edition 2021
# DISTRO_NAME=php_amd64
# ROOTFS_FILE=php-musl_amd64_2023-02-13_12-04-rootfs.tar.zst
# SHA256SUM=e3a857e4ed26a07bdb7b51f3fd9f9f85f99906381b94fe0dd3deeb9ca9120410
# BUILD_DATE=20230213
# BUILD_TAG=2023-02-13
# STATUS=completed
# VERSION=latest01
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-13
begin = 2023-02-13 12:02:35.496923946+00:00
start-sync_0 = 12:03:35
start-zstd = 12:03:41
start-sync_1 = 12:04:20
end-sync_1 = 12:04:26
end = 2023-02-13 12:04:26.600665732+00:00

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
PHP 8.2.2 (cli) (built: Feb 11 2023 10:19:55) (NTS)
Copyright (c) The PHP Group
Zend Engine v4.2.2, Copyright (c) Zend Technologies
'''

[other]
phpize_deps = 'autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c'
php_extra_configure_args = '--enable-embed'
php_cflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_cppflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_ldflags = '-Wl,-O1 -pie'
gpg_keys = '39B641343D8C104B2B146DC3F9C39DC0B9698544 E60913E4DF209907D8E30D96659A97C9CF2A795A 1198C0117593497A5EC5C199286AF1F9897469DC'
php_url = 'https://www.php.net/distributions/php-8.2.2.tar.xz'
php_src_url = 'https://www.php.net/distributions/php-8.2.2.tar.xz.asc'
```
