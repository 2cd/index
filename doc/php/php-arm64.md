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
tag = ["latest", "2022-06-06"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "php_arm64_2022-06-06_12-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "645e4d80b2f6f51a21fbdd38c87dc979a74cb36a6724478d394c3d9eb7f7adf6"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "457M"
tar_bytes = 478166528

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "99M"
zstd_bytes = 102761027

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220523"
previous_tag = "2022-05-23"
previous_file = "php_arm64_2022-05-23_12-09-rootfs.tar.zst"
previous_sha256 = "b8d04f49ae8b8484beae01e55b24fb964c3f0e7203449b0606a76e8b14c23ab1"

current_version = "latest01"
current_date = "20220606"
old_file = "php_arm64_2022-05-09_12-09-rootfs.tar.zst"
old_sha256 = "e457a774ec636bfb6873a496b5a95838077c55cb1f6b2e894b0539ede5a60198"
# edition 2021
# DISTRO_NAME=php_arm64
# ROOTFS_FILE=php_arm64_2022-06-06_12-09-rootfs.tar.zst
# SHA256SUM=645e4d80b2f6f51a21fbdd38c87dc979a74cb36a6724478d394c3d9eb7f7adf6
# BUILD_DATE=20220606
# BUILD_TAG=2022-06-06
# STATUS=completed
# VERSION=latest01
# END_TIME=12:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-06
begin = 2022-06-06 12:02:34.462814299+00:00
start-sync_0 = 12:05:10
start-zstd = 12:05:26
start-sync_1 = 12:09:30
end-sync_1 = 12:09:44
end = 2022-06-06 12:09:44.184418571+00:00

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u3) 2.31'
php = '''
PHP 8.1.6 (cli) (built: May 28 2022 04:42:45) (NTS)
Copyright (c) The PHP Group
Zend Engine v4.1.6, Copyright (c) Zend Technologies
'''

[other]
phpize_deps = 'autoconf 		dpkg-dev 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c'
php_extra_configure_args = '--enable-embed'
php_cflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_cppflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_ldflags = '-Wl,-O1 -pie'
gpg_keys = '528995BFEDFBA7191D46839EF9BA0ADA31CBD89E 39B641343D8C104B2B146DC3F9C39DC0B9698544 F1F692238FBC1666E5A5CCD4199F9DFEF6FFBAFD'
php_url = 'https://www.php.net/distributions/php-8.1.6.tar.xz'
php_src_url = 'https://www.php.net/distributions/php-8.1.6.tar.xz.asc'
```
