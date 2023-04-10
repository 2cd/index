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
tag = ["latest", "2023-04-10"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "php_amd64_2023-04-10_12-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "2b7c2f39b91c74e696011d3f51f0f6b58b8f0be4bcb4b1289b4b8d1726025056"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "492M"
tar_bytes = 514875904

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "98M"
zstd_bytes = 101837332

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230327"
previous_tag = "2023-03-27"
previous_file = "php_amd64_2023-03-27_12-08-rootfs.tar.zst"
previous_sha256 = "32839ad92517080fd1c4cbf64b480f159d7b70110e9acc6c8ace707f8990d1d8"

current_version = "latest01"
current_date = "20230410"
old_file = "php_amd64_2023-03-13_12-08-rootfs.tar.zst"
old_sha256 = "5327de36def8f14a24169214ae4f2e8ef869685678d83ca8d6db17573dacdd96"
# edition 2021
# DISTRO_NAME=php_amd64
# ROOTFS_FILE=php_amd64_2023-04-10_12-08-rootfs.tar.zst
# SHA256SUM=2b7c2f39b91c74e696011d3f51f0f6b58b8f0be4bcb4b1289b4b8d1726025056
# BUILD_DATE=20230410
# BUILD_TAG=2023-04-10
# STATUS=completed
# VERSION=latest01
# END_TIME=12:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-10
begin = 2023-04-10 12:02:32.716539247+00:00
start-sync_0 = 12:03:36
start-zstd = 12:03:47
start-sync_1 = 12:08:08
end-sync_1 = 12:08:18
end = 2023-04-10 12:08:18.960849726+00:00

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
PHP 8.2.4 (cli) (built: Mar 27 2023 22:35:18) (NTS)
Copyright (c) The PHP Group
Zend Engine v4.2.4, Copyright (c) Zend Technologies
'''

[other]
phpize_deps = 'autoconf 		dpkg-dev 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c'
php_extra_configure_args = '--enable-embed'
php_cflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_cppflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_ldflags = '-Wl,-O1 -pie'
gpg_keys = '39B641343D8C104B2B146DC3F9C39DC0B9698544 E60913E4DF209907D8E30D96659A97C9CF2A795A 1198C0117593497A5EC5C199286AF1F9897469DC'
php_url = 'https://www.php.net/distributions/php-8.2.4.tar.xz'
php_src_url = 'https://www.php.net/distributions/php-8.2.4.tar.xz.asc'
```
