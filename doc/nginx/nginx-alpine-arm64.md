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
tag = ["alpine", "2022-04-18", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false
syntax_version = "0.0.0-alpha.3"

[file]
name = "nginx-musl_arm64_2022-04-18_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d8862d6519f6989929b8ab4c1228b305778d80edac168f60a673520a285e425d"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "33M"
tar_bytes = 34188288

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "9.0M"
zstd_bytes = 9403072

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220404"
previous_tag = "2022-04-04"
previous_file = "nginx-musl_arm64_2022-04-04_11-04-rootfs.tar.zst"
previous_sha256 = "ce3c5befdc842a9d1776c56807a5f6309fe57de877df00bd812a9bccf306a5c9"

current_version = "latest01"
current_date = "20220418"
old_file = "nginx-musl_arm64_2022-03-21_12-04-rootfs.tar.zst"
old_sha256 = "81d3a598c2bf71d446f5b087441b0d45f3f9e7a191020f9c3e67b74613394b29"
# edition 2021
# DISTRO_NAME=nginx_arm64
# ROOTFS_FILE=nginx-musl_arm64_2022-04-18_12-04-rootfs.tar.zst
# SHA256SUM=d8862d6519f6989929b8ab4c1228b305778d80edac168f60a673520a285e425d
# BUILD_DATE=20220418
# BUILD_TAG=2022-04-18
# STATUS=completed
# VERSION=latest01
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-18
begin = 2022-04-18 12:02:32.223877731+00:00
start-sync_0 = 12:03:48
start-zstd = 12:03:54
start-sync_1 = 12:04:13
end-sync_1 = 12:04:18
end = 2022-04-18 12:04:18.142146186+00:00

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
LANG = "C.UTF-8"

[version]
ldd = 'musl libc (aarch64) Version 1.2.2'
nginx = '1.21.6'
njs = '0.7.2'
pkg_release = '1'
```
