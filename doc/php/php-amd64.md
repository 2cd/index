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
tag = ["latest", "2022-12-05"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "php_amd64_2022-12-05_12-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d153ea1a33611eec06db359256497f301a5b7bf11504f662124b7491e9a5cde9"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "491M"
tar_bytes = 514275840

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "97M"
zstd_bytes = 101492992

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221121"
previous_tag = "2022-11-21"
previous_file = "php_amd64_2022-11-21_12-08-rootfs.tar.zst"
previous_sha256 = "5834463ee3a867df580b21388969cd5af09ab87878d17c00a3aed9f474735706"

current_version = "latest01"
current_date = "20221205"
old_file = "php_amd64_2022-11-07_12-08-rootfs.tar.zst"
old_sha256 = "a39b0150b5b12c654c79bf256290a8addd0e50e54b308903974138cb25eb469a"
# edition 2021
# DISTRO_NAME=php_amd64
# ROOTFS_FILE=php_amd64_2022-12-05_12-08-rootfs.tar.zst
# SHA256SUM=d153ea1a33611eec06db359256497f301a5b7bf11504f662124b7491e9a5cde9
# BUILD_DATE=20221205
# BUILD_TAG=2022-12-05
# STATUS=completed
# VERSION=latest01
# END_TIME=12:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-05
begin = 2022-12-05 12:02:30.210878139+00:00
start-sync_0 = 12:03:32
start-zstd = 12:03:43
start-sync_1 = 12:07:52
end-sync_1 = 12:08:03
end = 2022-12-05 12:08:03.453302369+00:00

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u5) 2.31'
php = '''
PHP 8.1.13 (cli) (built: Nov 29 2022 02:32:03) (NTS)
Copyright (c) The PHP Group
Zend Engine v4.1.13, Copyright (c) Zend Technologies
'''

[other]
phpize_deps = 'autoconf 		dpkg-dev 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c'
php_extra_configure_args = '--enable-embed'
php_cflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_cppflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_ldflags = '-Wl,-O1 -pie'
gpg_keys = '528995BFEDFBA7191D46839EF9BA0ADA31CBD89E 39B641343D8C104B2B146DC3F9C39DC0B9698544 F1F692238FBC1666E5A5CCD4199F9DFEF6FFBAFD'
php_url = 'https://www.php.net/distributions/php-8.1.13.tar.xz'
php_src_url = 'https://www.php.net/distributions/php-8.1.13.tar.xz.asc'
```
