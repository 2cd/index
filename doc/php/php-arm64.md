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
tag = ["latest", "2023-12-04"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "php_arm64_2023-12-04_12-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "4c4aa9fa1032acc2ed1e96a2ca02eb2a92875e7b4ebd668b5bd65bf8a2d52f52"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "538M"
tar_bytes = 563094016

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "102M"
zstd_bytes = 106920513

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231023"
previous_tag = "2023-10-23"
previous_file = "php_arm64_2023-10-23_12-10-rootfs.tar.zst"
previous_sha256 = "9bb2a5c727f7e945674ad050e98e4bdccd398e645e14a2ce74e53b9c1b6aa37c"

current_version = "latest02"
current_date = "20231204"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=php_arm64
# ROOTFS_FILE=php_arm64_2023-12-04_12-10-rootfs.tar.zst
# SHA256SUM=4c4aa9fa1032acc2ed1e96a2ca02eb2a92875e7b4ebd668b5bd65bf8a2d52f52
# BUILD_DATE=20231204
# BUILD_TAG=2023-12-04
# STATUS=completed
# VERSION=latest02
# END_TIME=12:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-12-04
begin = 2023-12-04 12:02:37.657546530+00:00
start-sync_0 = 12:05:43
start-zstd = 12:05:56
start-sync_1 = 12:09:53
end-sync_1 = 12:10:06
end = 2023-12-04 12:10:06.954447159+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-9+deb12u3) 2.36'
php = '''
PHP 8.3.0 (cli) (built: Nov 27 2023 20:52:51) (NTS)
Copyright (c) The PHP Group
Zend Engine v4.3.0, Copyright (c) Zend Technologies
'''

[other]
phpize_deps = 'autoconf 		dpkg-dev 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c'
php_extra_configure_args = '--enable-embed'
php_cflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_cppflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_ldflags = '-Wl,-O1 -pie'
gpg_keys = '1198C0117593497A5EC5C199286AF1F9897469DC C28D937575603EB4ABB725861C0779DC5C0A9DE4 AFD8691FDAEDF03BDF6E460563F15A9B715376CA'
php_url = 'https://www.php.net/distributions/php-8.3.0.tar.xz'
php_src_url = 'https://www.php.net/distributions/php-8.3.0.tar.xz.asc'
```
