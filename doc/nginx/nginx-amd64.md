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
tag = ["latest", "2022-04-18"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false
syntax_version = "0.0.0-alpha.3"

[file]
name = "nginx_amd64_2022-04-18_12-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "01919be8f1e7c4251fdba268fe20998458c41660446ee2c02df135bb896998b0"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "163M"
tar_bytes = 170081792

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "40M"
zstd_bytes = 41552827

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220404"
previous_tag = "2022-04-04"
previous_file = "nginx_amd64_2022-04-04_11-06-rootfs.tar.zst"
previous_sha256 = "17ea40f3cfaec6e65774df60df6f3f910a062c2a85a4fe7f8d44a994468288e4"

current_version = "latest01"
current_date = "20220418"
old_file = "nginx_amd64_2022-03-21_12-05-rootfs.tar.zst"
old_sha256 = "4ff4ad4bcda616cc26564becffa0fb0ed9c0b86830f4c649b5165b58f293ee0f"
# edition 2021
# DISTRO_NAME=nginx_amd64
# ROOTFS_FILE=nginx_amd64_2022-04-18_12-05-rootfs.tar.zst
# SHA256SUM=01919be8f1e7c4251fdba268fe20998458c41660446ee2c02df135bb896998b0
# BUILD_DATE=20220418
# BUILD_TAG=2022-04-18
# STATUS=completed
# VERSION=latest01
# END_TIME=12:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-18
begin = 2022-04-18 12:02:30.981244294+00:00
start-sync_0 = 12:03:40
start-zstd = 12:03:49
start-sync_1 = 12:05:23
end-sync_1 = 12:05:31
end = 2022-04-18 12:05:31.101614007+00:00

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
