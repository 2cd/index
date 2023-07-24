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
tag = ["alpine", "2023-07-24", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "nginx-musl_arm64_2023-07-24_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "e7fa090a8220eb141dfda402c25e9f2640579d7be9f42edef51f25891a1af7b4"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "59M"
tar_bytes = 60923904

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "14M"
zstd_bytes = 14247935

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230710"
previous_tag = "2023-07-10"
previous_file = "nginx-musl_arm64_2023-07-10_12-04-rootfs.tar.zst"
previous_sha256 = "f425be90ac76dae35d40bbb597c1396510ab51a8a43ad57055182b7fd133600f"

current_version = "latest02"
current_date = "20230724"
old_file = "nginx-musl_arm64_2023-06-26_12-04-rootfs.tar.zst"
old_sha256 = "a341dcc51bc197ee8ebe6ee1198a7cf726510574a54ec247f70bf7343afa0a01"
# edition 2021
# DISTRO_NAME=nginx_arm64
# ROOTFS_FILE=nginx-musl_arm64_2023-07-24_12-04-rootfs.tar.zst
# SHA256SUM=e7fa090a8220eb141dfda402c25e9f2640579d7be9f42edef51f25891a1af7b4
# BUILD_DATE=20230724
# BUILD_TAG=2023-07-24
# STATUS=completed
# VERSION=latest02
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-24
begin = 2023-07-24 12:02:35.789054376+00:00
start-sync_0 = 12:03:36
start-zstd = 12:03:46
start-sync_1 = 12:04:15
end-sync_1 = 12:04:23
end = 2023-07-24 12:04:23.180792310+00:00

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
ldd = 'musl libc (aarch64) Version 1.2.3'
nginx = '1.25.1'
njs = '0.7.12'
pkg_release = '1'
```
