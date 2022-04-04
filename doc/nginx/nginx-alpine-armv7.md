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
tag = ["alpine", "2022-04-04", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "nginx-musl_armhf_2022-04-04_11-03.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "3867e7952948f2d50cc047d0a2ad288e42e508a678b3ab20717301fa092be46a"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "25M"
tar_bytes = 25351168

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "8.4M"
zstd_bytes = 8731673

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220321"
previous_tag = "2022-03-21"
previous_file = "nginx-musl_armhf_2022-03-21_12-03-rootfs.tar.zst"
previous_sha256 = "e05eb7e2b8f810044f446430c72e0b1e2b4465814014a7ad434215998fd0f6b8"

current_version = "latest02"
current_date = "20220404"
old_file = "nginx-musl_armhf_2022-03-07_12-03-rootfs.tar.zst"
old_sha256 = "81a80f3cc3434b4600f71795f08889d6f958c471a9b674963d94ce5ae22ab626"
# edition 2021
# DISTRO_NAME=nginx_armhf
# ROOTFS_FILE=nginx-musl_armhf_2022-04-04_11-03-rootfs.tar.zst
# SHA256SUM=3867e7952948f2d50cc047d0a2ad288e42e508a678b3ab20717301fa092be46a
# BUILD_DATE=20220404
# BUILD_TAG=2022-04-04
# STATUS=completed
# VERSION=latest02
# END_TIME=11:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-04
begin = 2022-04-04 11:02:33.996171060+00:00
start-sync_0 = 11:03:14
start-zstd = 11:03:19
start-sync_1 = 11:03:30
end-sync_1 = 11:03:35
end = 2022-04-04 11:03:35.245129759+00:00

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
ldd = 'musl libc (armhf) Version 1.2.2'
nginx = '1.21.6'
njs = '0.7.2'
pkg_release = '1'
```
