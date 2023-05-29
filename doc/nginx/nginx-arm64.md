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
tag = ["latest", "2023-05-29"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "nginx_arm64_2023-05-29_12-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "41d1d1654cbe97b6452f0acc61fb146ec04efbca4db24154e526c971408a114c"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "157M"
tar_bytes = 163861504

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "39M"
zstd_bytes = 40773139

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230515"
previous_tag = "2023-05-15"
previous_file = "nginx_arm64_2023-05-15_12-07-rootfs.tar.zst"
previous_sha256 = "80e6ca2c49337d2c5beaf57a4c84c0e96c3b5a5905f71cc1dbc900e8bba99c8d"

current_version = "latest01"
current_date = "20230529"
old_file = "nginx_arm64_2023-05-01_12-07-rootfs.tar.zst"
old_sha256 = "5477c16d29cfd0c53cb646d9afcee1e928d04f6503a7063d038b51ba44f73bf2"
# edition 2021
# DISTRO_NAME=nginx_arm64
# ROOTFS_FILE=nginx_arm64_2023-05-29_12-06-rootfs.tar.zst
# SHA256SUM=41d1d1654cbe97b6452f0acc61fb146ec04efbca4db24154e526c971408a114c
# BUILD_DATE=20230529
# BUILD_TAG=2023-05-29
# STATUS=completed
# VERSION=latest01
# END_TIME=12:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-05-29
begin = 2023-05-29 12:02:42.117478463+00:00
start-sync_0 = 12:04:47
start-zstd = 12:04:58
start-sync_1 = 12:06:31
end-sync_1 = 12:06:39
end = 2023-05-29 12:06:39.619871246+00:00

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
LANG = "en_US.UTF-8"

[version]
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u6) 2.31'
nginx = '1.25.0'
njs = '0.7.12'
pkg_release = '1~bullseye'
```
