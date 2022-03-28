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
tag = ["latest", "2022-03-28"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "php_amd64_2022-03-28_11-08.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "0dc5e37a44930c2144cfb8f0bf9252139610feeec39085bee330a47184d42461"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "490M"
tar_bytes = 513765376

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "97M"
zstd_bytes = 101284419

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220324"
previous_tag = "2022-03-24"
previous_file = "php_amd64_2022-03-24_12-32-rootfs.tar.zst"
previous_sha256 = "75a1529b4b0a3d15d632e867c489a6f0278ca164cdefb109799192a55333641a"

current_version = "latest01"
current_date = "20220328"
old_file = "php_amd64_2022-03-14_12-08-rootfs.tar.zst"
old_sha256 = "dc66a4e5cf61649db6445389835afdb44a530cba7b3fde72537dbff00af2254c"
# edition 2021
# DISTRO_NAME=php_amd64
# ROOTFS_FILE=php_amd64_2022-03-28_11-08-rootfs.tar.zst
# SHA256SUM=0dc5e37a44930c2144cfb8f0bf9252139610feeec39085bee330a47184d42461
# BUILD_DATE=20220328
# BUILD_TAG=2022-03-28
# STATUS=completed
# VERSION=latest01
# END_TIME=11:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-28
begin = 2022-03-28 11:02:28.520021720+00:00
start-sync_0 = 11:03:36
start-zstd = 11:03:51
start-sync_1 = 11:08:37
end-sync_1 = 11:08:49
end = 2022-03-28 11:08:49.641113018+00:00

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
PHP 8.1.4 (cli) (built: Mar 18 2022 18:10:55) (NTS)
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
