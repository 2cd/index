# nginx-arm64

## How to run it?

```sh
docker run \
    -it \
    --name nginx-arm64 \
    cake233/nginx-arm64
```

## How to exec shell?

```sh
docker exec -it nginx-arm64 bash
```

## nginx-arm64.toml

```toml
[main]
name = "nginx"
tag = ["latest", "2022-04-04"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "nginx_arm64_2022-04-04_11-08.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "14455e95ac39f50418ca04a2d499f2da41f49be6553e2bd9764785c1185f9e71"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "156M"
tar_bytes = 162945536

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "39M"
zstd_bytes = 40611687

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220321"
previous_tag = "2022-03-21"
previous_file = "nginx_arm64_2022-03-21_12-06-rootfs.tar.zst"
previous_sha256 = "0f1dedc603b0189054a9288c60afd62d5b1464e9015eb22c0fe8ae2ccfed1e51"

current_version = "latest02"
current_date = "20220404"
old_file = "nginx_arm64_2022-03-07_12-07-rootfs.tar.zst"
old_sha256 = "d313fcf04d9f41d35342ceb4471af735e2ff03ed01040267abb48aed037491ff"
# edition 2021
# DISTRO_NAME=nginx_arm64
# ROOTFS_FILE=nginx_arm64_2022-04-04_11-08-rootfs.tar.zst
# SHA256SUM=14455e95ac39f50418ca04a2d499f2da41f49be6553e2bd9764785c1185f9e71
# BUILD_DATE=20220404
# BUILD_TAG=2022-04-04
# STATUS=completed
# VERSION=latest02
# END_TIME=11:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-04
begin = 2022-04-04 11:04:15.712397582+00:00
start-sync_0 = 11:06:25
start-zstd = 11:06:34
start-sync_1 = 11:08:16
end-sync_1 = 11:08:22
end = 2022-04-04 11:08:23.016327490+00:00

[server]
repo = "cake233/nginx-arm64"

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
LANG = "en_US.UTF-8"

[version]
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u3) 2.31'
nginx = '1.21.6'
njs = '0.7.2'
pkg_release = '1~bullseye'
```
