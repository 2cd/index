# nginx-amd64

## How to run it?

```sh
docker run \
    -it \
    --name nginx-amd64 \
    cake233/nginx-amd64
```

## How to exec shell?

```sh
docker exec -it nginx-amd64 bash
```

## nginx-amd64.toml

```toml
[main]
name = "nginx"
tag = ["latest", "2023-02-20"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "nginx_amd64_2023-02-20_12-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "232ed7b8ebf2c8796fd280dc14711893ebb27496ff9438c094e9a702069e1c8e"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "163M"
tar_bytes = 170398720

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "40M"
zstd_bytes = 41586422

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230206"
previous_tag = "2023-02-06"
previous_file = "nginx_amd64_2023-02-06_12-05-rootfs.tar.zst"
previous_sha256 = "ebc0d90daf8f9dc5f917da8aec17f291b68ba543e8c9cb7133477d1557c07728"

current_version = "latest02"
current_date = "20230220"
old_file = "nginx_amd64_2023-01-23_12-05-rootfs.tar.zst"
old_sha256 = "7fe95ec12b459afe0e83527c521f2c06d6a0fd8f9f22b7f19c2f61aaf61ab084"
# edition 2021
# DISTRO_NAME=nginx_amd64
# ROOTFS_FILE=nginx_amd64_2023-02-20_12-05-rootfs.tar.zst
# SHA256SUM=232ed7b8ebf2c8796fd280dc14711893ebb27496ff9438c094e9a702069e1c8e
# BUILD_DATE=20230220
# BUILD_TAG=2023-02-20
# STATUS=completed
# VERSION=latest02
# END_TIME=12:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-20
begin = 2023-02-20 12:02:35.974004111+00:00
start-sync_0 = 12:03:25
start-zstd = 12:03:39
start-sync_1 = 12:05:09
end-sync_1 = 12:05:21
end = 2023-02-20 12:05:21.202471699+00:00

[server]
repo = "cake233/nginx-amd64"

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
nginx = '1.23.3'
njs = '0.7.9'
pkg_release = '1~bullseye'
```
