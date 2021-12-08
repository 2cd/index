# nginx-arm64

## How to run it?

```shell
docker run \
    -it \
    --name nginx-arm64 \
    cake233/nginx-arm64
```

## How to exec shell?

```shell
    docker exec -it nginx-arm64 bash
```

## nginx-arm64.toml

```toml
[main]
name = "nginx"
tag = ["latest", "2021-12-08"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "nginx_arm64_2021-12-08_01-10.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "a320ae665613b8a19d5f582f5c9c98b005d2d3a3600cb824dad6f1159b39ee4a"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "156M"
tar_bytes = 162939392

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "40M"
zstd_bytes = 41533004

[compatibility]
compatible_mode = true

last_version = "latest01"

# The value is &str, not int
last_date = "20211128"
last_tag = "2021-11-28"
last_file = "nginx_arm64_2021-11-28_23-03-rootfs.tar.zst"
last_sha256 = "9afd8c9f18c2eca2a9b15c5820e284a03c5cdabc513dbbe3329a177b0dac3648"

current_version = "latest02"
current_date = "20211208"
old_file = "nginx_arm64+latest-2021_11-01-rootfs.tar.zst"
old_sha256 = ""
# edition 2021
# DISTRO_NAME=nginx_arm64
# ROOTFS_FILE=nginx_arm64_2021-12-08_01-10-rootfs.tar.zst
# SHA256SUM=a320ae665613b8a19d5f582f5c9c98b005d2d3a3600cb824dad6f1159b39ee4a
# BUILD_DATE=20211208
# BUILD_TAG=2021-12-08
# STATUS=completed
# VERSION=latest02
# END_TIME=01:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-08
begin = 2021-12-08 01:06:16.403941887+00:00
start-sync_0 = 01:08:59
start-zstd = 01:09:16
start-sync_1 = 01:10:10
end-sync_1 = 01:10:22
end = 2021-12-08 01:10:22.950013835+00:00

[server]
repo = "cake233/nginx-arm64"

[server.node1]
name = "cn"
current = false
last = true
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = false
last = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
last = true
in_sync = false
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"

[version]
nginx = '1.21.4'
njs = '0.7.0'
pkg_release = '1~bullseye'
```
