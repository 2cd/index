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
tag = ["latest", "2022-03-01"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "php_arm64_2022-03-01_18-57.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "c18483dea9cae13dd778519caa14d1d1b8e490e4d2124584fed403a7bcd3c896"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "456M"
tar_bytes = 478072832

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "122M"
zstd_bytes = 127426809

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220214"
previous_tag = "2022-02-14"
previous_file = "php_arm64_2022-02-14_12-07-rootfs.tar.zst"
previous_sha256 = "a42675fac7a873699b0931547be8201c865b1057bd9b70c5a3b669cf7a1094ba"

current_version = "latest01"
current_date = "20220301"
old_file = "php_arm64_2022-01-31_12-06-rootfs.tar.zst"
old_sha256 = "d0f2c7b0e38e79595ddde67483079e35f23016863a5946bb8fed81a3bce6165b"
# edition 2021
# DISTRO_NAME=php_arm64
# ROOTFS_FILE=php_arm64_2022-03-01_18-57-rootfs.tar.zst
# SHA256SUM=c18483dea9cae13dd778519caa14d1d1b8e490e4d2124584fed403a7bcd3c896
# BUILD_DATE=20220301
# BUILD_TAG=2022-03-01
# STATUS=completed
# VERSION=latest01
# END_TIME=18:57

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-01
begin = 2022-03-01 18:53:56.635026906+00:00
start-sync_0 = 18:56:19
start-zstd = 18:56:33
start-sync_1 = 18:57:43
end-sync_1 = 18:57:58
end = 2022-03-01 18:57:58.448805180+00:00

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u2) 2.31'
php = '''
PHP 8.1.3 (cli) (built: Feb 18 2022 19:44:36) (NTS)
Copyright (c) The PHP Group
Zend Engine v4.1.3, Copyright (c) Zend Technologies
'''

[other]
phpize_deps = 'autoconf 		dpkg-dev 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c'
php_extra_configure_args = '--enable-embed'
php_cflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_cppflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_ldflags = '-Wl,-O1 -pie'
gpg_keys = '528995BFEDFBA7191D46839EF9BA0ADA31CBD89E 39B641343D8C104B2B146DC3F9C39DC0B9698544 F1F692238FBC1666E5A5CCD4199F9DFEF6FFBAFD'
php_url = 'https://www.php.net/distributions/php-8.1.3.tar.xz'
php_src_url = 'https://www.php.net/distributions/php-8.1.3.tar.xz.asc'
```
