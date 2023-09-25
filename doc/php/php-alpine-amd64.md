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
tag = ["alpine", "2023-09-25", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "php-musl_amd64_2023-09-25_12-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "1194c72907e6ac97f9a88e40d12024a693275b1e32ef31df963b5d0adf97c5b1"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "104M"
tar_bytes = 108276736

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "26M"
zstd_bytes = 26570205

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230911"
previous_tag = "2023-09-11"
previous_file = "php-musl_amd64_2023-09-11_12-04-rootfs.tar.zst"
previous_sha256 = "42889655ea0206043c83ca5c9938a1b6660e0cbdef16b1d71598b3e3baea5eff"

current_version = "latest01"
current_date = "20230925"
old_file = "php-musl_amd64_2023-08-28_12-03-rootfs.tar.zst"
old_sha256 = "d50c13959d83825d846565c04e375ad08cb4100ca5f14ee709750c594ae62a85"
# edition 2021
# DISTRO_NAME=php_amd64
# ROOTFS_FILE=php-musl_amd64_2023-09-25_12-05-rootfs.tar.zst
# SHA256SUM=1194c72907e6ac97f9a88e40d12024a693275b1e32ef31df963b5d0adf97c5b1
# BUILD_DATE=20230925
# BUILD_TAG=2023-09-25
# STATUS=completed
# VERSION=latest01
# END_TIME=12:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-25
begin = 2023-09-25 12:02:41.374787778+00:00
start-sync_0 = 12:03:59
start-zstd = 12:04:11
start-sync_1 = 12:05:05
end-sync_1 = 12:05:16
end = 2023-09-25 12:05:16.790916394+00:00

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
PHP 8.2.10 (cli) (built: Sep  2 2023 07:06:06) (NTS)
Copyright (c) The PHP Group
Zend Engine v4.2.10, Copyright (c) Zend Technologies
'''

[other]
phpize_deps = 'autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c'
php_extra_configure_args = '--enable-embed'
php_cflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_cppflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_ldflags = '-Wl,-O1 -pie'
gpg_keys = '39B641343D8C104B2B146DC3F9C39DC0B9698544 E60913E4DF209907D8E30D96659A97C9CF2A795A 1198C0117593497A5EC5C199286AF1F9897469DC'
php_url = 'https://www.php.net/distributions/php-8.2.10.tar.xz'
php_src_url = 'https://www.php.net/distributions/php-8.2.10.tar.xz.asc'
```
