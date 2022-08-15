# php-amd64

## How to run it?

```sh
docker run \
    -it \
    --name php-amd64 \
    cake233/php-amd64
```

## How to exec shell?

```sh
docker exec -it php-amd64 bash
```

## php-amd64.toml

```toml
[main]
name = "php"
tag = ["latest", "2022-08-15"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "php_amd64_2022-08-15_12-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "e9ac623b2a318097b58dccb8cf1501694e559e5472196204246f21f018870eeb"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "491M"
tar_bytes = 513932288

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "97M"
zstd_bytes = 101334780

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220704"
previous_tag = "2022-07-04"
previous_file = "php_amd64_2022-07-04_12-08-rootfs.tar.zst"
previous_sha256 = "93563ed77bb24e861ecc9a98f760e5146fdec0b39e6f38813d2a7a392a2939ae"

current_version = "latest01"
current_date = "20220815"
old_file = "php_amd64_2022-06-20_12-08-rootfs.tar.zst"
old_sha256 = "c90d48ebfabe0f1aaf0168dd8ed8388222a03cb4d9648fcbea38f254e47cf22b"
# edition 2021
# DISTRO_NAME=php_amd64
# ROOTFS_FILE=php_amd64_2022-08-15_12-09-rootfs.tar.zst
# SHA256SUM=e9ac623b2a318097b58dccb8cf1501694e559e5472196204246f21f018870eeb
# BUILD_DATE=20220815
# BUILD_TAG=2022-08-15
# STATUS=completed
# VERSION=latest01
# END_TIME=12:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-15
begin = 2022-08-15 12:02:35.921509662+00:00
start-sync_0 = 12:03:58
start-zstd = 12:04:19
start-sync_1 = 12:08:46
end-sync_1 = 12:09:02
end = 2022-08-15 12:09:02.935561208+00:00

[server]
repo = "cake233/php-amd64"

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u3) 2.31'
php = '''
PHP 8.1.9 (cli) (built: Aug  4 2022 21:02:10) (NTS)
Copyright (c) The PHP Group
Zend Engine v4.1.9, Copyright (c) Zend Technologies
'''

[other]
phpize_deps = 'autoconf 		dpkg-dev 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c'
php_extra_configure_args = '--enable-embed'
php_cflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_cppflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_ldflags = '-Wl,-O1 -pie'
gpg_keys = '528995BFEDFBA7191D46839EF9BA0ADA31CBD89E 39B641343D8C104B2B146DC3F9C39DC0B9698544 F1F692238FBC1666E5A5CCD4199F9DFEF6FFBAFD'
php_url = 'https://www.php.net/distributions/php-8.1.9.tar.xz'
php_src_url = 'https://www.php.net/distributions/php-8.1.9.tar.xz.asc'
```
