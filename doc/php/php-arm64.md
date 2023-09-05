# php-arm64

## How to run it?

```sh
docker run \
    -it \
    --name php-arm64 \
    cake233/php-arm64
```

## How to exec shell?

```sh
docker exec -it php-arm64 bash
```

## php-arm64.toml

```toml
[main]
name = "php"
tag = ["latest", "2023-08-28"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "php_arm64_2023-08-28_12-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a1f22d2f292af66452591e6b4911148bbd68b6d3452ced09e627a10c47ae2f35"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "533M"
tar_bytes = 558428160

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "102M"
zstd_bytes = 106403540

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20230828"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=php_arm64
# ROOTFS_FILE=php_arm64_2023-08-28_12-10-rootfs.tar.zst
# SHA256SUM=a1f22d2f292af66452591e6b4911148bbd68b6d3452ced09e627a10c47ae2f35
# BUILD_DATE=20230828
# BUILD_TAG=2023-08-28
# STATUS=completed
# VERSION=latest01
# END_TIME=12:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-28
begin = 2023-08-28 12:02:42.067711234+00:00
start-sync_0 = 12:04:59
start-zstd = 12:05:11
start-sync_1 = 12:10:09
end-sync_1 = 12:10:22
end = 2023-08-28 12:10:22.746919485+00:00

[server]
repo = "cake233/php-arm64"

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
LANG = "en_US.UTF-8"
PHP_INI_DIR = '/usr/local/etc/php'

[version]
ldd = 'ldd (Debian GLIBC 2.36-9+deb12u1) 2.36'
php = '''
PHP 8.2.9 (cli) (built: Aug 17 2023 22:42:30) (NTS)
Copyright (c) The PHP Group
Zend Engine v4.2.9, Copyright (c) Zend Technologies
'''

[other]
phpize_deps = 'autoconf 		dpkg-dev 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c'
php_extra_configure_args = '--enable-embed'
php_cflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_cppflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_ldflags = '-Wl,-O1 -pie'
gpg_keys = '39B641343D8C104B2B146DC3F9C39DC0B9698544 E60913E4DF209907D8E30D96659A97C9CF2A795A 1198C0117593497A5EC5C199286AF1F9897469DC'
php_url = 'https://www.php.net/distributions/php-8.2.9.tar.xz'
php_src_url = 'https://www.php.net/distributions/php-8.2.9.tar.xz.asc'
```