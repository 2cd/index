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
tag = ["alpine", "2023-02-06", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "nginx-musl_arm64_2023-02-06_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "23ec327c5c991ce01ce96bd1a93c9ee326abc50a9fdc1ff471b3b849d0b8dfc7"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "58M"
tar_bytes = 60282368

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "14M"
zstd_bytes = 14062138

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230123"
previous_tag = "2023-01-23"
previous_file = "nginx-musl_arm64_2023-01-23_12-04-rootfs.tar.zst"
previous_sha256 = "45a7f002160b67305c378a7587c3c42ffb00eab15c94c0ecfb0d71523671933a"

current_version = "latest01"
current_date = "20230206"
old_file = "nginx-musl_arm64_2023-01-09_12-03-rootfs.tar.zst"
old_sha256 = "70afd98f7e578f8c3bdacce30f588d99ebafc86de6b831f311cbc8f4cddd4f2f"
# edition 2021
# DISTRO_NAME=nginx_arm64
# ROOTFS_FILE=nginx-musl_arm64_2023-02-06_12-04-rootfs.tar.zst
# SHA256SUM=23ec327c5c991ce01ce96bd1a93c9ee326abc50a9fdc1ff471b3b849d0b8dfc7
# BUILD_DATE=20230206
# BUILD_TAG=2023-02-06
# STATUS=completed
# VERSION=latest01
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-06
begin = 2023-02-06 12:02:32.929745425+00:00
start-sync_0 = 12:03:24
start-zstd = 12:03:32
start-sync_1 = 12:03:55
end-sync_1 = 12:04:01
end = 2023-02-06 12:04:01.574107994+00:00

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
nginx = '1.23.3'
njs = '0.7.9'
pkg_release = '1'
```
