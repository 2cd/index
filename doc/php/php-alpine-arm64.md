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
tag = ["alpine", "2022-04-25", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false
syntax_version = "0.0.0-alpha.3"

[file]
name = "php-musl_arm64_2022-04-25_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "99b5f28dbe61ff359325125305d7a3a7d4afc1e6388dd67618eb8216fd7d6844"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "91M"
tar_bytes = 94966784

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "25M"
zstd_bytes = 25259909

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220411"
previous_tag = "2022-04-11"
previous_file = "php-musl_arm64_2022-04-11_11-04-rootfs.tar.zst"
previous_sha256 = "b825d5c8aac170620fa59f62b45f91decb669fd1890de9f66883bb9ed6b389a5"

current_version = "latest01"
current_date = "20220425"
old_file = "php-musl_arm64_2022-03-28_11-04-rootfs.tar.zst"
old_sha256 = "c7387f827b4ab92b43c917567c6381a78538018ec21a3f125d352c7a7f94669c"
# edition 2021
# DISTRO_NAME=php_arm64
# ROOTFS_FILE=php-musl_arm64_2022-04-25_12-04-rootfs.tar.zst
# SHA256SUM=99b5f28dbe61ff359325125305d7a3a7d4afc1e6388dd67618eb8216fd7d6844
# BUILD_DATE=20220425
# BUILD_TAG=2022-04-25
# STATUS=completed
# VERSION=latest01
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-25
begin = 2022-04-25 12:02:34.292786185+00:00
start-sync_0 = 12:03:34
start-zstd = 12:03:48
start-sync_1 = 12:04:28
end-sync_1 = 12:04:39
end = 2022-04-25 12:04:39.930897687+00:00

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
ldd = 'musl libc (aarch64) Version 1.2.2'
php = '''
PHP 8.1.5 (cli) (built: Apr 19 2022 00:18:07) (NTS)
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
