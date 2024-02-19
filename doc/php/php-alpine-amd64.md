# php-alpine-amd64

## How to run it?

```sh
docker run \
    -it \
    --name php-alpine-amd64 \
    cake233/php-alpine-amd64
```

## How to exec shell?

```sh
docker exec -it php-alpine-amd64 bash
```

## php-alpine-amd64.toml

```toml
[main]
name = "php"
tag = ["alpine", "2024-02-19", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "php-musl_amd64_2024-02-19_12-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "0e9547e3e44e9bb40630e5c4265b986fba7ed16e90548d7c7750b7624d3aab47"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "111M"
tar_bytes = 115716608

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "27M"
zstd_bytes = 27404726

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231120"
previous_tag = "2023-11-20"
previous_file = "php-musl_amd64_2023-11-20_12-05-rootfs.tar.zst"
previous_sha256 = "c9bbda16e1a9bce9675c56a1d8799678728c7d9d3a181481c3a80be3ff26ccde"

current_version = "latest01"
current_date = "20240219"
old_file = "php-musl_amd64_2023-10-23_12-05-rootfs.tar.zst"
old_sha256 = "e5eee15e3400abcc76314fa15f6ddd70cb5ea852a1d21bfd7a1a000a62cb021f"
# edition 2021
# DISTRO_NAME=php_amd64
# ROOTFS_FILE=php-musl_amd64_2024-02-19_12-05-rootfs.tar.zst
# SHA256SUM=0e9547e3e44e9bb40630e5c4265b986fba7ed16e90548d7c7750b7624d3aab47
# BUILD_DATE=20240219
# BUILD_TAG=2024-02-19
# STATUS=completed
# VERSION=latest01
# END_TIME=12:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-02-19
begin = 2024-02-19 12:02:38.386298245+00:00
start-sync_0 = 12:04:32
start-zstd = 12:04:39
start-sync_1 = 12:05:19
end-sync_1 = 12:05:26
end = 2024-02-19 12:05:26.198050285+00:00

[server]
repo = "cake233/php-alpine-amd64"

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
LANG = "C.UTF-8"
PHP_INI_DIR = '/usr/local/etc/php'

[version]
ldd = 'musl libc (x86_64) Version 1.2.4_git20230717'
php = '''
PHP 8.3.3 (cli) (built: Feb 16 2024 21:25:21) (NTS)
Copyright (c) The PHP Group
Zend Engine v4.3.3, Copyright (c) Zend Technologies
'''

[other]
phpize_deps = 'autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c'
php_extra_configure_args = '--enable-embed'
php_cflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_cppflags = '-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64'
php_ldflags = '-Wl,-O1 -pie'
gpg_keys = '1198C0117593497A5EC5C199286AF1F9897469DC C28D937575603EB4ABB725861C0779DC5C0A9DE4 AFD8691FDAEDF03BDF6E460563F15A9B715376CA'
php_url = 'https://www.php.net/distributions/php-8.3.3.tar.xz'
php_src_url = 'https://www.php.net/distributions/php-8.3.3.tar.xz.asc'
```
