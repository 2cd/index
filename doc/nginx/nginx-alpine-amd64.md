# nginx-alpine-amd64

## How to run it?

```sh
docker run \
    -it \
    --name nginx-alpine-amd64 \
    cake233/nginx-alpine-amd64
```

## How to exec shell?

```sh
docker exec -it nginx-alpine-amd64 bash
```

## nginx-alpine-amd64.toml

```toml
[main]
name = "nginx"
tag = ["alpine", "2023-02-20", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "nginx-musl_amd64_2023-02-20_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c58344f368fce10431e14c328c1e4f779b3b43873b580231cad76e65638753a2"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "52M"
tar_bytes = 53953024

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "15M"
zstd_bytes = 14816731

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230206"
previous_tag = "2023-02-06"
previous_file = "nginx-musl_amd64_2023-02-06_12-03-rootfs.tar.zst"
previous_sha256 = "7db6981e0fa787a6079f622bc4b6457d1c1a59574eafa2e4c037f1243fa3571e"

current_version = "latest02"
current_date = "20230220"
old_file = "nginx-musl_amd64_2023-01-23_12-04-rootfs.tar.zst"
old_sha256 = "11fa3f4af30564de62c6b17bb9be6767e15ef36d89e7f1b7551819911cb13fb3"
# edition 2021
# DISTRO_NAME=nginx_amd64
# ROOTFS_FILE=nginx-musl_amd64_2023-02-20_12-04-rootfs.tar.zst
# SHA256SUM=c58344f368fce10431e14c328c1e4f779b3b43873b580231cad76e65638753a2
# BUILD_DATE=20230220
# BUILD_TAG=2023-02-20
# STATUS=completed
# VERSION=latest02
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-20
begin = 2023-02-20 12:02:38.902047239+00:00
start-sync_0 = 12:03:22
start-zstd = 12:03:30
start-sync_1 = 12:03:56
end-sync_1 = 12:04:03
end = 2023-02-20 12:04:03.825530693+00:00

[server]
repo = "cake233/nginx-alpine-amd64"

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
ldd = 'musl libc (x86_64) Version 1.2.3'
nginx = '1.23.3'
njs = '0.7.9'
pkg_release = '1'
```
