# php-alpine-armv7

## How to run it?

```sh
docker run \
    -it \
    --name php-alpine-armv7 \
    cake233/php-alpine-armv7
```

## How to exec shell?

```sh
docker exec -it php-alpine-armv7 bash
```

## php-alpine-armv7.toml

```toml
[main]
name = "php"
tag = ["alpine", "2023-09-11", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "php-musl_armhf_2023-09-11_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "166580b0c7ae6a43c181f586456b0a4fee6f713ed19ddce02f67d0bcc4f08a0a"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "78M"
tar_bytes = 81596416

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "24M"
zstd_bytes = 24894631

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230828"
previous_tag = "2023-08-28"
previous_file = "php-musl_armhf_2023-08-28_12-04-rootfs.tar.zst"
previous_sha256 = "4e50c85ea1e256fa7d8448aecf455f39148ecb1ec279dc0af7e4fb2dd78bbcda"

current_version = "latest02"
current_date = "20230911"
old_file = "php-musl_armhf_2023-07-31_12-03-rootfs.tar.zst"
old_sha256 = "8a79298fa998679e20a3f22dd046d66bde061b18be10debc7a6aefb112841329"
# edition 2021
# DISTRO_NAME=php_armhf
# ROOTFS_FILE=php-musl_armhf_2023-09-11_12-04-rootfs.tar.zst
# SHA256SUM=166580b0c7ae6a43c181f586456b0a4fee6f713ed19ddce02f67d0bcc4f08a0a
# BUILD_DATE=20230911
# BUILD_TAG=2023-09-11
# STATUS=completed
# VERSION=latest02
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-11
begin = 2023-09-11 12:02:41.352623751+00:00
start-sync_0 = 12:03:50
start-zstd = 12:03:58
start-sync_1 = 12:04:29
end-sync_1 = 12:04:38
end = 2023-09-11 12:04:38.381381504+00:00

[server]
repo = "cake233/php-alpine-armv7"

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
ldd = 'musl libc (armhf) Version 1.2.4'
php = '''
PHP 8.2.10 (cli) (built: Sep  2 2023 03:22:08) (NTS)
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
