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
tag = ["alpine", "2022-05-15", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "nginx-musl_armhf_2022-05-15_15-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "fb9607dacf9aacf539901737314de6bb5f280e3f85966927013430be03fa6a19"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "25M"
tar_bytes = 25347072

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "8.4M"
zstd_bytes = 8744060

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220502"
previous_tag = "2022-05-02"
previous_file = "nginx-musl_armhf_2022-05-02_12-04-rootfs.tar.zst"
previous_sha256 = "dd5b17083820074630f406b5e1f8594c36378673603d3d9e791c4153b4eb4656"

current_version = "latest01"
current_date = "20220515"
old_file = "nginx-musl_armhf_2022-04-18_12-03-rootfs.tar.zst"
old_sha256 = "f4636c27f6019c0f94057bf4e47d833d9e2b857df498d0f58c6efb9b8cd660b5"
# edition 2021
# DISTRO_NAME=nginx_armhf
# ROOTFS_FILE=nginx-musl_armhf_2022-05-15_15-04-rootfs.tar.zst
# SHA256SUM=fb9607dacf9aacf539901737314de6bb5f280e3f85966927013430be03fa6a19
# BUILD_DATE=20220515
# BUILD_TAG=2022-05-15
# STATUS=completed
# VERSION=latest01
# END_TIME=15:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-15
begin = 2022-05-15 15:02:40.019810363+00:00
start-sync_0 = 15:03:35
start-zstd = 15:03:43
start-sync_1 = 15:03:54
end-sync_1 = 15:04:01
end = 2022-05-15 15:04:01.824502268+00:00

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
ldd = 'musl libc (armhf) Version 1.2.2'
nginx = '1.21.6'
njs = '0.7.2'
pkg_release = '1'
```
