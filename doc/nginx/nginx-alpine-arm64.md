# nginx-alpine-arm64

## How to run it?

```sh
docker run \
    -it \
    --name nginx-alpine-arm64 \
    cake233/nginx-alpine-arm64
```

## How to exec shell?

```sh
docker exec -it nginx-alpine-arm64 bash
```

## nginx-alpine-arm64.toml

```toml
[main]
name = "nginx"
tag = ["alpine", "2023-09-04", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "nginx-musl_arm64_2023-09-04_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8a8fdbefc5c1d5b21d603011c10d8c9be6f1718ad5590e7c76d5b2140ecd870e"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "59M"
tar_bytes = 61597696

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "14M"
zstd_bytes = 14651997

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20230904"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=nginx_arm64
# ROOTFS_FILE=nginx-musl_arm64_2023-09-04_12-04-rootfs.tar.zst
# SHA256SUM=8a8fdbefc5c1d5b21d603011c10d8c9be6f1718ad5590e7c76d5b2140ecd870e
# BUILD_DATE=20230904
# BUILD_TAG=2023-09-04
# STATUS=completed
# VERSION=latest01
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-04
begin = 2023-09-04 12:02:48.467295223+00:00
start-sync_0 = 12:04:06
start-zstd = 12:04:11
start-sync_1 = 12:04:36
end-sync_1 = 12:04:41
end = 2023-09-04 12:04:41.785730385+00:00

[server]
repo = "cake233/nginx-alpine-arm64"

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
ldd = 'musl libc (aarch64) Version 1.2.4'
nginx = '1.25.2'
njs = '0.8.0'
pkg_release = '1'
```