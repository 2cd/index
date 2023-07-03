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
tag = ["alpine", "2023-07-03", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "php-musl_amd64_2023-07-03_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "6022fe0d646212a6cf7e0e7dfd26e108115ee15cfb471527999252473e83888b"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "104M"
tar_bytes = 108192256

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "26M"
zstd_bytes = 26510361

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230619"
previous_tag = "2023-06-19"
previous_file = "php-musl_amd64_2023-06-19_12-05-rootfs.tar.zst"
previous_sha256 = "6e83b8a0c20fec9131fe86d74fa0b78da3629aec42c226eaaf34fc0c7ae3fba9"

current_version = "latest01"
current_date = "20230703"
old_file = "php-musl_amd64_2023-06-05_12-04-rootfs.tar.zst"
old_sha256 = "820741f9667da7716f38ee29f23b6860d10032e1c758a90f393a1f11b1cca39f"
# edition 2021
# DISTRO_NAME=php_amd64
# ROOTFS_FILE=php-musl_amd64_2023-07-03_12-04-rootfs.tar.zst
# SHA256SUM=6022fe0d646212a6cf7e0e7dfd26e108115ee15cfb471527999252473e83888b
# BUILD_DATE=20230703
# BUILD_TAG=2023-07-03
# STATUS=completed
# VERSION=latest01
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-03
begin = 2023-07-03 12:02:35.267952770+00:00
start-sync_0 = 12:03:11
start-zstd = 12:03:17
start-sync_1 = 12:04:01
end-sync_1 = 12:04:07
end = 2023-07-03 12:04:07.701966958+00:00

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
PHP 8.2.7 (cli) (built: Jun 15 2023 00:57:00) (NTS)
Copyright (c) The PHP Group
Zend Engine v4.2.7, Copyright (c) Zend Technologies
'''

[other]
phpize_deps = 'autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c'
php_extra_configure_args = '--enable-embed'
php_cflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_cppflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_ldflags = '-Wl,-O1 -pie'
gpg_keys = '39B641343D8C104B2B146DC3F9C39DC0B9698544 E60913E4DF209907D8E30D96659A97C9CF2A795A 1198C0117593497A5EC5C199286AF1F9897469DC'
php_url = 'https://www.php.net/distributions/php-8.2.7.tar.xz'
php_src_url = 'https://www.php.net/distributions/php-8.2.7.tar.xz.asc'
```
