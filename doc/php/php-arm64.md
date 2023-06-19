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
tag = ["latest", "2023-06-19"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "php_arm64_2023-06-19_12-11.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "cdeb378566aab55a32caaf8da28dc7769608884c2468819810d6168b7af623cd"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "533M"
tar_bytes = 558337536

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "102M"
zstd_bytes = 106385630

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230605"
previous_tag = "2023-06-05"
previous_file = "php_arm64_2023-06-05_12-09-rootfs.tar.zst"
previous_sha256 = "8fdf5f0f3b84cd7828d8bafd936535d80751b54b6de32ac0a87b42c19fd042e9"

current_version = "latest02"
current_date = "20230619"
old_file = "php_arm64_2023-05-22_12-10-rootfs.tar.zst"
old_sha256 = "0fcc37a86c205611d4d53a40781a5c1bd4a7def62bac38a30737687b50e87490"
# edition 2021
# DISTRO_NAME=php_arm64
# ROOTFS_FILE=php_arm64_2023-06-19_12-11-rootfs.tar.zst
# SHA256SUM=cdeb378566aab55a32caaf8da28dc7769608884c2468819810d6168b7af623cd
# BUILD_DATE=20230619
# BUILD_TAG=2023-06-19
# STATUS=completed
# VERSION=latest02
# END_TIME=12:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-19
begin = 2023-06-19 12:02:45.409663194+00:00
start-sync_0 = 12:06:01
start-zstd = 12:06:14
start-sync_1 = 12:11:10
end-sync_1 = 12:11:21
end = 2023-06-19 12:11:21.990646050+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-9) 2.36'
php = '''
PHP 8.2.7 (cli) (built: Jun 13 2023 23:05:53) (NTS)
Copyright (c) The PHP Group
Zend Engine v4.2.7, Copyright (c) Zend Technologies
'''

[other]
phpize_deps = 'autoconf 		dpkg-dev 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c'
php_extra_configure_args = '--enable-embed'
php_cflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_cppflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_ldflags = '-Wl,-O1 -pie'
gpg_keys = '39B641343D8C104B2B146DC3F9C39DC0B9698544 E60913E4DF209907D8E30D96659A97C9CF2A795A 1198C0117593497A5EC5C199286AF1F9897469DC'
php_url = 'https://www.php.net/distributions/php-8.2.7.tar.xz'
php_src_url = 'https://www.php.net/distributions/php-8.2.7.tar.xz.asc'
```
