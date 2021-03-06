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
tag = ["alpine", "2022-07-11", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "nginx-musl_armhf_2022-07-11_12-03.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "94f63a985713586c3779e0c96e6ffce31bf6bca0934d895b5eb95b9afb2d159a"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "25M"
tar_bytes = 25419776

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "8.4M"
zstd_bytes = 8778596

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220627"
previous_tag = "2022-06-27"
previous_file = "nginx-musl_armhf_2022-06-27_12-03-rootfs.tar.zst"
previous_sha256 = "aa67d0dc7841d19d04ac71f6e9ec7763c28804fea81976661290666a048e4588"

current_version = "latest01"
current_date = "20220711"
old_file = "nginx-musl_armhf_2022-06-13_12-03-rootfs.tar.zst"
old_sha256 = "bb7e1b79988113c6ffc0139b1f4bb8640b8d269b19b073885e4320f5f0ef951b"
# edition 2021
# DISTRO_NAME=nginx_armhf
# ROOTFS_FILE=nginx-musl_armhf_2022-07-11_12-03-rootfs.tar.zst
# SHA256SUM=94f63a985713586c3779e0c96e6ffce31bf6bca0934d895b5eb95b9afb2d159a
# BUILD_DATE=20220711
# BUILD_TAG=2022-07-11
# STATUS=completed
# VERSION=latest01
# END_TIME=12:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-11
begin = 2022-07-11 12:02:34.487679220+00:00
start-sync_0 = 12:03:22
start-zstd = 12:03:28
start-sync_1 = 12:03:40
end-sync_1 = 12:03:45
end = 2022-07-11 12:03:45.248441689+00:00

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
ldd = 'musl libc (armhf) Version 1.2.3'
nginx = '1.23.0'
njs = '0.7.5'
pkg_release = '1'
```
