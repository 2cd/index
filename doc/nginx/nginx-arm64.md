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
tag = ["latest", "2022-02-07"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "nginx_arm64_2022-02-07_12-06.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "9c1d2d8b2ac054b691bb32cc27e1007d98be65cdc6a2b99011a442bf89460b70"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "156M"
tar_bytes = 162952192

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "40M"
zstd_bytes = 41593931

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220124"
previous_tag = "2022-01-24"
previous_file = "nginx_arm64_2022-01-24_12-06-rootfs.tar.zst"
previous_sha256 = "2656d687ef85d4ed0458eae046bc7c5c124458aca5136c4a0083bd427181256b"

current_version = "latest02"
current_date = "20220207"
old_file = "nginx_arm64_2022-01-10_12-06-rootfs.tar.zst"
old_sha256 = "ce9b630636f90cd26786bcb9755a1e2c140fbf6cd4333da43657464cd6d3a379"
# edition 2021
# DISTRO_NAME=nginx_arm64
# ROOTFS_FILE=nginx_arm64_2022-02-07_12-06-rootfs.tar.zst
# SHA256SUM=9c1d2d8b2ac054b691bb32cc27e1007d98be65cdc6a2b99011a442bf89460b70
# BUILD_DATE=20220207
# BUILD_TAG=2022-02-07
# STATUS=completed
# VERSION=latest02
# END_TIME=12:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-07
begin = 2022-02-07 12:02:37.553683208+00:00
start-sync_0 = 12:05:20
start-zstd = 12:05:30
start-sync_1 = 12:06:31
end-sync_1 = 12:06:39
end = 2022-02-07 12:06:39.390205633+00:00

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u2) 2.31'
nginx = '1.21.6'
njs = '0.7.2'
pkg_release = '1~bullseye'
```
