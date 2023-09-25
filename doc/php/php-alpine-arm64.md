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
tag = ["alpine", "2023-09-25", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "php-musl_arm64_2023-09-25_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "88e3e598f77045a2ac1035f438f61febe400f07b16be16b0a61c88ac25eff12e"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "104M"
tar_bytes = 109015552

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "26M"
zstd_bytes = 26634395

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230911"
previous_tag = "2023-09-11"
previous_file = "php-musl_arm64_2023-09-11_12-05-rootfs.tar.zst"
previous_sha256 = "621a5acd9af0188c65a23fcaf6cf60266c369944583ea493039168adb45b9bc4"

current_version = "latest01"
current_date = "20230925"
old_file = "php-musl_arm64_2023-08-28_12-04-rootfs.tar.zst"
old_sha256 = "882d23a4f4634116d8e021d78a68c9dc47d01c76da15c7762af91d1713b00217"
# edition 2021
# DISTRO_NAME=php_arm64
# ROOTFS_FILE=php-musl_arm64_2023-09-25_12-04-rootfs.tar.zst
# SHA256SUM=88e3e598f77045a2ac1035f438f61febe400f07b16be16b0a61c88ac25eff12e
# BUILD_DATE=20230925
# BUILD_TAG=2023-09-25
# STATUS=completed
# VERSION=latest01
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-25
begin = 2023-09-25 12:02:35.494863333+00:00
start-sync_0 = 12:03:42
start-zstd = 12:03:48
start-sync_1 = 12:04:31
end-sync_1 = 12:04:37
end = 2023-09-25 12:04:37.569847867+00:00

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
ldd = 'musl libc (aarch64) Version 1.2.4'
php = '''
PHP 8.2.10 (cli) (built: Sep  2 2023 05:46:35) (NTS)
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
