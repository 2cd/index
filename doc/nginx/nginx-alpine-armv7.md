# nginx-alpine-armv7

## How to run it?

```sh
docker run \
    -it \
    --name nginx-alpine-armv7 \
    cake233/nginx-alpine-armv7
```

## How to exec shell?

```sh
docker exec -it nginx-alpine-armv7 bash
```

## nginx-alpine-armv7.toml

```toml
[main]
name = "nginx"
tag = ["alpine", "2024-01-01", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "nginx-musl_armhf_2024-01-01_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f5bfa57fd7ed80eac8b12d80a0985a63470db329414e03e4050e26d135aed10e"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "35M"
tar_bytes = 36516352

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "13M"
zstd_bytes = 13158121

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231127"
previous_tag = "2023-11-27"
previous_file = "nginx-musl_armhf_2023-11-27_12-04-rootfs.tar.zst"
previous_sha256 = "d747743a84b4bc42417eb61902c09b5023ca9fbd515cb130a0003a2cca395a11"

current_version = "latest01"
current_date = "20240101"
old_file = "nginx-musl_armhf_2023-11-13_12-05-rootfs.tar.zst"
old_sha256 = "5e7928be8fef2b4f40ce5f9fa7a83d3e844550fbc8d55737ffd522374d6061cf"
# edition 2021
# DISTRO_NAME=nginx_armhf
# ROOTFS_FILE=nginx-musl_armhf_2024-01-01_12-04-rootfs.tar.zst
# SHA256SUM=f5bfa57fd7ed80eac8b12d80a0985a63470db329414e03e4050e26d135aed10e
# BUILD_DATE=20240101
# BUILD_TAG=2024-01-01
# STATUS=completed
# VERSION=latest01
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-01-01
begin = 2024-01-01 12:02:35.780384859+00:00
start-sync_0 = 12:03:53
start-zstd = 12:03:59
start-sync_1 = 12:04:14
end-sync_1 = 12:04:19
end = 2024-01-01 12:04:19.753788116+00:00

[server]
repo = "cake233/nginx-alpine-armv7"

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

[version]
ldd = 'musl libc (armhf) Version 1.2.4'
nginx = '1.25.3'
njs = '0.8.2'
pkg_release = '1'
```
