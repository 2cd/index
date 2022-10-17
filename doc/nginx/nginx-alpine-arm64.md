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
tag = ["alpine", "2022-10-17", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "nginx-musl_arm64_2022-10-17_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c1a2a75942865dd372101b0fd37a0429a00ffb7773c3bcd22f0067951fa77e1b"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "33M"
tar_bytes = 34230784

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "9.1M"
zstd_bytes = 9454117

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221003"
previous_tag = "2022-10-03"
previous_file = "nginx-musl_arm64_2022-10-03_12-04-rootfs.tar.zst"
previous_sha256 = "a42f7b898b12e629327c8b2ddea9b8b189727d60259d2896046445e0e487bbff"

current_version = "latest01"
current_date = "20221017"
old_file = "nginx-musl_arm64_2022-09-19_12-04-rootfs.tar.zst"
old_sha256 = "2758c296d4a14fe732050731b77c4a529eeea98b2c919d73ebcffe25f468a153"
# edition 2021
# DISTRO_NAME=nginx_arm64
# ROOTFS_FILE=nginx-musl_arm64_2022-10-17_12-04-rootfs.tar.zst
# SHA256SUM=c1a2a75942865dd372101b0fd37a0429a00ffb7773c3bcd22f0067951fa77e1b
# BUILD_DATE=20221017
# BUILD_TAG=2022-10-17
# STATUS=completed
# VERSION=latest01
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-17
begin = 2022-10-17 12:02:29.045051053+00:00
start-sync_0 = 12:03:28
start-zstd = 12:03:37
start-sync_1 = 12:03:53
end-sync_1 = 12:04:00
end = 2022-10-17 12:04:00.903362380+00:00

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
nginx = '1.23.1'
njs = '0.7.6'
pkg_release = '1'
```
