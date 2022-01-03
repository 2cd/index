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
tag = ["latest", "2022-01-03"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "php_amd64_2022-01-03_12-05.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "792d22780eb45691621421d464d82fc1bc81c3489bb4d42081915efde76e3299"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "490M"
tar_bytes = 513718784

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "126M"
zstd_bytes = 131463362

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211220"
previous_tag = "2021-12-20"
previous_file = "php_amd64_2021-12-20_12-05-rootfs.tar.zst"
previous_sha256 = "ccb64549f317d847df374305b1e4dad510dfcb2275f02fb06f1a20f829f5d02b"

current_version = "latest02"
current_date = "20220103"
old_file = "php_amd64_2021-12-06_20-07-rootfs.tar.zst"
old_sha256 = ""
# edition 2021
# DISTRO_NAME=php_amd64
# ROOTFS_FILE=php_amd64_2022-01-03_12-05-rootfs.tar.zst
# SHA256SUM=792d22780eb45691621421d464d82fc1bc81c3489bb4d42081915efde76e3299
# BUILD_DATE=20220103
# BUILD_TAG=2022-01-03
# STATUS=completed
# VERSION=latest02
# END_TIME=12:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-03
begin = 2022-01-03 12:02:28.123701349+00:00
start-sync_0 = 12:03:19
start-zstd = 12:03:31
start-sync_1 = 12:04:55
end-sync_1 = 12:05:09
end = 2022-01-03 12:05:09.669607639+00:00

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u2) 2.31'
php = '''
PHP 8.1.1 (cli) (built: Dec 21 2021 19:35:25) (NTS)
Copyright (c) The PHP Group
Zend Engine v4.1.1, Copyright (c) Zend Technologies
'''

[other]
phpize_deps = 'autoconf 		dpkg-dev 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c'
php_extra_configure_args = '--enable-embed'
php_cflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_cppflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_ldflags = '-Wl,-O1 -pie'
gpg_keys = '528995BFEDFBA7191D46839EF9BA0ADA31CBD89E 39B641343D8C104B2B146DC3F9C39DC0B9698544 F1F692238FBC1666E5A5CCD4199F9DFEF6FFBAFD'
php_url = 'https://www.php.net/distributions/php-8.1.1.tar.xz'
php_src_url = 'https://www.php.net/distributions/php-8.1.1.tar.xz.asc'
```
