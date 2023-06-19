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
tag = ["alpine", "2023-06-19", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "php-musl_armhf_2023-06-19_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "7f552b938ae3855367f87aa83bdd7c0a128cc2a15d4f242b85ec6f2a29aa4502"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "78M"
tar_bytes = 81582080

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "24M"
zstd_bytes = 24869821

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230605"
previous_tag = "2023-06-05"
previous_file = "php-musl_armhf_2023-06-05_12-04-rootfs.tar.zst"
previous_sha256 = "af6bcc75c293b7321ad744cfbcd49b9223aa8ed56d6dd0322e00456ee61b62a7"

current_version = "latest01"
current_date = "20230619"
old_file = "php-musl_armhf_2023-05-22_12-05-rootfs.tar.zst"
old_sha256 = "12822ce651929f97890eaaa47e8701afd57ba1aa8bc786172e05584b278f02d4"
# edition 2021
# DISTRO_NAME=php_armhf
# ROOTFS_FILE=php-musl_armhf_2023-06-19_12-04-rootfs.tar.zst
# SHA256SUM=7f552b938ae3855367f87aa83bdd7c0a128cc2a15d4f242b85ec6f2a29aa4502
# BUILD_DATE=20230619
# BUILD_TAG=2023-06-19
# STATUS=completed
# VERSION=latest01
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-19
begin = 2023-06-19 12:02:45.059609138+00:00
start-sync_0 = 12:04:06
start-zstd = 12:04:12
start-sync_1 = 12:04:43
end-sync_1 = 12:04:49
end = 2023-06-19 12:04:49.417718109+00:00

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
PHP 8.2.7 (cli) (built: Jun 15 2023 05:59:12) (NTS)
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
