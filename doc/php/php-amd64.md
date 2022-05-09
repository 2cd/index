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
tag = ["latest", "2022-05-09"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "php_amd64_2022-05-09_12-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f9554ae320f1f623ad4b9243af5b863ffa561733d6454116838fdc8b537e13fc"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "491M"
tar_bytes = 513850368

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "97M"
zstd_bytes = 101284233

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220425"
previous_tag = "2022-04-25"
previous_file = "php_amd64_2022-04-25_12-09-rootfs.tar.zst"
previous_sha256 = "5604e57fd8d25a207161cd5a4484ffe4594070a43451f67463913fbd6af54710"

current_version = "latest02"
current_date = "20220509"
old_file = "php_amd64_2022-04-11_11-09-rootfs.tar.zst"
old_sha256 = "dd80c6cd3d33dcb52987426c6e3365234e4ea3ce091537d8ebed4f2aa808e1f7"
# edition 2021
# DISTRO_NAME=php_amd64
# ROOTFS_FILE=php_amd64_2022-05-09_12-09-rootfs.tar.zst
# SHA256SUM=f9554ae320f1f623ad4b9243af5b863ffa561733d6454116838fdc8b537e13fc
# BUILD_DATE=20220509
# BUILD_TAG=2022-05-09
# STATUS=completed
# VERSION=latest02
# END_TIME=12:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-09
begin = 2022-05-09 12:02:38.642789314+00:00
start-sync_0 = 12:03:57
start-zstd = 12:04:16
start-sync_1 = 12:09:05
end-sync_1 = 12:09:22
end = 2022-05-09 12:09:22.390900933+00:00

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
PHP 8.1.5 (cli) (built: Apr 20 2022 11:20:18) (NTS)
Copyright (c) The PHP Group
Zend Engine v4.1.5, Copyright (c) Zend Technologies
'''

[other]
phpize_deps = 'autoconf 		dpkg-dev 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c'
php_extra_configure_args = '--enable-embed'
php_cflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_cppflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_ldflags = '-Wl,-O1 -pie'
gpg_keys = '528995BFEDFBA7191D46839EF9BA0ADA31CBD89E 39B641343D8C104B2B146DC3F9C39DC0B9698544 F1F692238FBC1666E5A5CCD4199F9DFEF6FFBAFD'
php_url = 'https://www.php.net/distributions/php-8.1.5.tar.xz'
php_src_url = 'https://www.php.net/distributions/php-8.1.5.tar.xz.asc'
```
