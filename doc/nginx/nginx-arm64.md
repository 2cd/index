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
tag = ["latest", "2022-11-28"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "nginx_arm64_2022-11-28_12-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "7750775e0bb9cfc3cc5fd070c15321ee4e7d2a37cd086d4466b2200a62c3ca4b"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "156M"
tar_bytes = 163122688

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "39M"
zstd_bytes = 40643999

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221114"
previous_tag = "2022-11-14"
previous_file = "nginx_arm64_2022-11-14_12-06-rootfs.tar.zst"
previous_sha256 = "6462feef53bf4a46c4b0695d9dd018b1548b2c20ed511c0d0324f6852778cc56"

current_version = "latest02"
current_date = "20221128"
old_file = "nginx_arm64_2022-10-31_12-07-rootfs.tar.zst"
old_sha256 = "40727e277719f629ba31b0e5b42a79c26d06b6d736a5bb00841e6d2397901c12"
# edition 2021
# DISTRO_NAME=nginx_arm64
# ROOTFS_FILE=nginx_arm64_2022-11-28_12-07-rootfs.tar.zst
# SHA256SUM=7750775e0bb9cfc3cc5fd070c15321ee4e7d2a37cd086d4466b2200a62c3ca4b
# BUILD_DATE=20221128
# BUILD_TAG=2022-11-28
# STATUS=completed
# VERSION=latest02
# END_TIME=12:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-28
begin = 2022-11-28 12:02:29.864121913+00:00
start-sync_0 = 12:05:26
start-zstd = 12:05:39
start-sync_1 = 12:07:33
end-sync_1 = 12:07:42
end = 2022-11-28 12:07:42.449582325+00:00

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u5) 2.31'
nginx = '1.23.2'
njs = '0.7.7'
pkg_release = '1~bullseye'
```
