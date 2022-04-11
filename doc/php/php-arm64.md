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
tag = ["latest", "2022-04-11"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false
syntax_version = "0.0.0-alpha.3"

[file]
name = "php_arm64_2022-04-11_11-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "967e3cac0e2dea6a742f85e9e8d8ad5e6500a68c875998fcb6a8dce0b1d860bc"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "456M"
tar_bytes = 478094848

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "99M"
zstd_bytes = 102804906

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220328"
previous_tag = "2022-03-28"
previous_file = "php_arm64_2022-03-28_11-10-rootfs.tar.zst"
previous_sha256 = "724d22cbb9c5e7518ca926f7fe163262017d2ff9ae45ea971ea95c5fa76da3ef"

current_version = "latest01"
current_date = "20220411"
old_file = "php_arm64_2022-03-24_12-33-rootfs.tar.zst"
old_sha256 = "9ef17bc1c8144fd9e08b67c3d9a1460a0473aa5f39cbde4825ad0fdae64316c8"
# edition 2021
# DISTRO_NAME=php_arm64
# ROOTFS_FILE=php_arm64_2022-04-11_11-09-rootfs.tar.zst
# SHA256SUM=967e3cac0e2dea6a742f85e9e8d8ad5e6500a68c875998fcb6a8dce0b1d860bc
# BUILD_DATE=20220411
# BUILD_TAG=2022-04-11
# STATUS=completed
# VERSION=latest01
# END_TIME=11:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-11
begin = 2022-04-11 11:02:35.263502793+00:00
start-sync_0 = 11:04:56
start-zstd = 11:05:08
start-sync_1 = 11:09:02
end-sync_1 = 11:09:13
end = 2022-04-11 11:09:13.718804185+00:00

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
LANG = "en_US.UTF-8"
PHP_INI_DIR = '/usr/local/etc/php'

[version]
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u3) 2.31'
php = '''
PHP 8.1.4 (cli) (built: Mar 29 2022 01:53:06) (NTS)
Copyright (c) The PHP Group
Zend Engine v4.1.4, Copyright (c) Zend Technologies
'''

[other]
phpize_deps = 'autoconf 		dpkg-dev 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c'
php_extra_configure_args = '--enable-embed'
php_cflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_cppflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_ldflags = '-Wl,-O1 -pie'
gpg_keys = '528995BFEDFBA7191D46839EF9BA0ADA31CBD89E 39B641343D8C104B2B146DC3F9C39DC0B9698544 F1F692238FBC1666E5A5CCD4199F9DFEF6FFBAFD'
php_url = 'https://www.php.net/distributions/php-8.1.4.tar.xz'
php_src_url = 'https://www.php.net/distributions/php-8.1.4.tar.xz.asc'
```
