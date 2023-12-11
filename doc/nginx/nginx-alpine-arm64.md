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
tag = ["alpine", "2023-12-11", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "nginx-musl_arm64_2023-12-11_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8446357e40326dd47321694fe9396bb09134c667d90756b59f28d32325ec5015"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "59M"
tar_bytes = 61679104

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "15M"
zstd_bytes = 14686357

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231127"
previous_tag = "2023-11-27"
previous_file = "nginx-musl_arm64_2023-11-27_12-04-rootfs.tar.zst"
previous_sha256 = "5707b55637d0b1d244d51d9fbf609fd262c01cadd6429a6d2522bb670535fbe4"

current_version = "latest01"
current_date = "20231211"
old_file = "nginx-musl_arm64_2023-11-13_12-04-rootfs.tar.zst"
old_sha256 = "2901b644b403349123e80198e62924a091084fb6bd3ed4c42dcea33a60870171"
# edition 2021
# DISTRO_NAME=nginx_arm64
# ROOTFS_FILE=nginx-musl_arm64_2023-12-11_12-04-rootfs.tar.zst
# SHA256SUM=8446357e40326dd47321694fe9396bb09134c667d90756b59f28d32325ec5015
# BUILD_DATE=20231211
# BUILD_TAG=2023-12-11
# STATUS=completed
# VERSION=latest01
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-12-11
begin = 2023-12-11 12:02:34.912260642+00:00
start-sync_0 = 12:04:07
start-zstd = 12:04:18
start-sync_1 = 12:04:38
end-sync_1 = 12:04:47
end = 2023-12-11 12:04:47.347972705+00:00

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
nginx = '1.25.3'
njs = '0.8.2'
pkg_release = '1'
```
