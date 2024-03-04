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
tag = ["latest", "2024-03-04"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "php_amd64_2024-03-04_12-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "2e8b41d34544d9ded33517cde1dd9c178abe40f35c54470127e1ec58b0fafd1d"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "542M"
tar_bytes = 567708672

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "100M"
zstd_bytes = 104594162

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231120"
previous_tag = "2023-11-20"
previous_file = "php_amd64_2023-11-20_12-09-rootfs.tar.zst"
previous_sha256 = "19e53070c24e2502fe1b79e0ea6ef76a992da5461c8bb17c2714885e640d7742"

current_version = "latest01"
current_date = "20240304"
old_file = "php_amd64_2023-10-23_12-10-rootfs.tar.zst"
old_sha256 = "762c0e191f8316b6160ce024ba746a5e43a99ceafb157038568da625efe95917"
# edition 2021
# DISTRO_NAME=php_amd64
# ROOTFS_FILE=php_amd64_2024-03-04_12-08-rootfs.tar.zst
# SHA256SUM=2e8b41d34544d9ded33517cde1dd9c178abe40f35c54470127e1ec58b0fafd1d
# BUILD_DATE=20240304
# BUILD_TAG=2024-03-04
# STATUS=completed
# VERSION=latest01
# END_TIME=12:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-03-04
begin = 2024-03-04 12:02:37.655822557+00:00
start-sync_0 = 12:04:05
start-zstd = 12:04:17
start-sync_1 = 12:08:44
end-sync_1 = 12:08:56
end = 2024-03-04 12:08:56.597673239+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-9+deb12u4) 2.36'
php = '''
PHP 8.3.3 (cli) (built: Feb 16 2024 20:53:43) (NTS)
Copyright (c) The PHP Group
Zend Engine v4.3.3, Copyright (c) Zend Technologies
'''

[other]
phpize_deps = 'autoconf 		dpkg-dev 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c'
php_extra_configure_args = '--enable-embed'
php_cflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_cppflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_ldflags = '-Wl,-O1 -pie'
gpg_keys = '1198C0117593497A5EC5C199286AF1F9897469DC C28D937575603EB4ABB725861C0779DC5C0A9DE4 AFD8691FDAEDF03BDF6E460563F15A9B715376CA'
php_url = 'https://www.php.net/distributions/php-8.3.3.tar.xz'
php_src_url = 'https://www.php.net/distributions/php-8.3.3.tar.xz.asc'
```
