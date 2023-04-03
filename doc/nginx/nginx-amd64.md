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
tag = ["latest", "2023-04-03"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "nginx_amd64_2023-04-03_12-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "bb8700e6a33436fb4351c013ab0f928a7f7db1d32678de9560d966db65c84c52"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "163M"
tar_bytes = 170710016

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "40M"
zstd_bytes = 41637360

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230320"
previous_tag = "2023-03-20"
previous_file = "nginx_amd64_2023-03-20_12-05-rootfs.tar.zst"
previous_sha256 = "c1ed8a66506fb987d82ecd2cc471b1b5abe01e763db6f1f0266770560f688aa0"

current_version = "latest01"
current_date = "20230403"
old_file = "nginx_amd64_2023-03-06_12-05-rootfs.tar.zst"
old_sha256 = "30d47e866cd60c639eed36478d51f5a542d6a7db07a29c9b42d74b3211560567"
# edition 2021
# DISTRO_NAME=nginx_amd64
# ROOTFS_FILE=nginx_amd64_2023-04-03_12-05-rootfs.tar.zst
# SHA256SUM=bb8700e6a33436fb4351c013ab0f928a7f7db1d32678de9560d966db65c84c52
# BUILD_DATE=20230403
# BUILD_TAG=2023-04-03
# STATUS=completed
# VERSION=latest01
# END_TIME=12:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-03
begin = 2023-04-03 12:02:39.778895087+00:00
start-sync_0 = 12:03:27
start-zstd = 12:03:35
start-sync_1 = 12:05:09
end-sync_1 = 12:05:17
end = 2023-04-03 12:05:17.068489821+00:00

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
nginx = '1.23.4'
njs = '0.7.11'
pkg_release = '1~bullseye'
```
