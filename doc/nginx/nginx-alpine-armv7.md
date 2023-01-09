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
tag = ["alpine", "2023-01-09", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "nginx-musl_armhf_2023-01-09_12-03.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "6a9c7b134a16944e19851d494f75e156cf198b3e3fafc3aa78085747b9723167"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "47M"
tar_bytes = 48389120

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "13M"
zstd_bytes = 12703500

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221226"
previous_tag = "2022-12-26"
previous_file = "nginx-musl_armhf_2022-12-26_12-04-rootfs.tar.zst"
previous_sha256 = "f2aed751fd3cf6e595f306063fa619227b7f7b9ed5aa3204a2c1c562c38e43db"

current_version = "latest01"
current_date = "20230109"
old_file = "nginx-musl_armhf_2022-12-12_12-03-rootfs.tar.zst"
old_sha256 = "1883d15dc777c45fe073c79e444bc41be9823c367fd3bd9c0001edab7cb7d013"
# edition 2021
# DISTRO_NAME=nginx_armhf
# ROOTFS_FILE=nginx-musl_armhf_2023-01-09_12-03-rootfs.tar.zst
# SHA256SUM=6a9c7b134a16944e19851d494f75e156cf198b3e3fafc3aa78085747b9723167
# BUILD_DATE=20230109
# BUILD_TAG=2023-01-09
# STATUS=completed
# VERSION=latest01
# END_TIME=12:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-09
begin = 2023-01-09 12:02:33.600592995+00:00
start-sync_0 = 12:03:24
start-zstd = 12:03:30
start-sync_1 = 12:03:44
end-sync_1 = 12:03:49
end = 2023-01-09 12:03:49.019974725+00:00

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
nginx = '1.23.3'
njs = '0.7.9'
pkg_release = '1'
```
