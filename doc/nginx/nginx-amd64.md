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
tag = ["latest", "2023-05-29"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "nginx_amd64_2023-05-29_12-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5626afb1f4a5fd1cf979572a811ccf78d2be4b1c1e9b0025d3cbc0cc8410df2d"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "164M"
tar_bytes = 171139584

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "40M"
zstd_bytes = 41772353

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230515"
previous_tag = "2023-05-15"
previous_file = "nginx_amd64_2023-05-15_12-05-rootfs.tar.zst"
previous_sha256 = "4e096b746bf28e26aea17257495f1c0753f53632b6c31272a31b4a4322ce4f07"

current_version = "latest01"
current_date = "20230529"
old_file = "nginx_amd64_2023-05-01_12-05-rootfs.tar.zst"
old_sha256 = "756b3fbb3464d8f72bf3c9ec426d967c0148245a5610ef08e49cbc24aac5d6b4"
# edition 2021
# DISTRO_NAME=nginx_amd64
# ROOTFS_FILE=nginx_amd64_2023-05-29_12-05-rootfs.tar.zst
# SHA256SUM=5626afb1f4a5fd1cf979572a811ccf78d2be4b1c1e9b0025d3cbc0cc8410df2d
# BUILD_DATE=20230529
# BUILD_TAG=2023-05-29
# STATUS=completed
# VERSION=latest01
# END_TIME=12:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-05-29
begin = 2023-05-29 12:02:40.256272201+00:00
start-sync_0 = 12:03:21
start-zstd = 12:03:29
start-sync_1 = 12:04:58
end-sync_1 = 12:05:05
end = 2023-05-29 12:05:05.885788782+00:00

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u6) 2.31'
nginx = '1.25.0'
njs = '0.7.12'
pkg_release = '1~bullseye'
```
