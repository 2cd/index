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
tag = ["alpine", "2024-02-05", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "php-musl_arm64_2024-02-05_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "21027e31a8213b016531ebef39847457fab105a7dfaf4fece715c61ecedbc7b2"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "108M"
tar_bytes = 112636416

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "27M"
zstd_bytes = 27395682

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231120"
previous_tag = "2023-11-20"
previous_file = "php-musl_arm64_2023-11-20_12-05-rootfs.tar.zst"
previous_sha256 = "884a869ba24133c9f50b96f7005399eb67d5079d9e36fae01cd3c6e9888122ec"

current_version = "latest01"
current_date = "20240205"
old_file = "php-musl_arm64_2023-10-23_12-05-rootfs.tar.zst"
old_sha256 = "7625f3c5bf5d73c1d833e95ad09717c603ea80c536b41bab9cd68c7480d3e6d9"
# edition 2021
# DISTRO_NAME=php_arm64
# ROOTFS_FILE=php-musl_arm64_2024-02-05_12-04-rootfs.tar.zst
# SHA256SUM=21027e31a8213b016531ebef39847457fab105a7dfaf4fece715c61ecedbc7b2
# BUILD_DATE=20240205
# BUILD_TAG=2024-02-05
# STATUS=completed
# VERSION=latest01
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-02-05
begin = 2024-02-05 12:02:35.571336784+00:00
start-sync_0 = 12:03:54
start-zstd = 12:04:00
start-sync_1 = 12:04:38
end-sync_1 = 12:04:44
end = 2024-02-05 12:04:44.098897393+00:00

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
PHP 8.3.2 (cli) (built: Jan 27 2024 07:30:52) (NTS)
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
