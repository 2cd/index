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
tag = ["alpine", "2022-10-03", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "nginx-musl_arm64_2022-10-03_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a42f7b898b12e629327c8b2ddea9b8b189727d60259d2896046445e0e487bbff"

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
zstd_bytes = 9450933

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220919"
previous_tag = "2022-09-19"
previous_file = "nginx-musl_arm64_2022-09-19_12-04-rootfs.tar.zst"
previous_sha256 = "2758c296d4a14fe732050731b77c4a529eeea98b2c919d73ebcffe25f468a153"

current_version = "latest02"
current_date = "20221003"
old_file = "nginx-musl_arm64_2022-09-05_12-04-rootfs.tar.zst"
old_sha256 = "ac5942de882b37824a93750eaa1095879ba6b2cf300625bad513d73ce0188fb6"
# edition 2021
# DISTRO_NAME=nginx_arm64
# ROOTFS_FILE=nginx-musl_arm64_2022-10-03_12-04-rootfs.tar.zst
# SHA256SUM=a42f7b898b12e629327c8b2ddea9b8b189727d60259d2896046445e0e487bbff
# BUILD_DATE=20221003
# BUILD_TAG=2022-10-03
# STATUS=completed
# VERSION=latest02
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-03
begin = 2022-10-03 12:02:27.907705214+00:00
start-sync_0 = 12:03:34
start-zstd = 12:03:43
start-sync_1 = 12:04:01
end-sync_1 = 12:04:09
end = 2022-10-03 12:04:09.285106171+00:00

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
