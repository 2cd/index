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
tag = ["alpine", "2023-04-03", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "nginx-musl_armhf_2023-04-03_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "78da5944db162fb1151302644608f5e44332612e8bd28fbeed842e3cd75bf4f1"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "47M"
tar_bytes = 48665600

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "13M"
zstd_bytes = 12742667

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230320"
previous_tag = "2023-03-20"
previous_file = "nginx-musl_armhf_2023-03-20_12-03-rootfs.tar.zst"
previous_sha256 = "383dc99aa72c25d9827e16f78733c01b6503df9ed6bd644601f0bebe3fbccc1d"

current_version = "latest01"
current_date = "20230403"
old_file = "nginx-musl_armhf_2023-03-06_12-03-rootfs.tar.zst"
old_sha256 = "77768acf5a51584947df9c3d0739376a95c048b362a7bea7fde66808c50af083"
# edition 2021
# DISTRO_NAME=nginx_armhf
# ROOTFS_FILE=nginx-musl_armhf_2023-04-03_12-04-rootfs.tar.zst
# SHA256SUM=78da5944db162fb1151302644608f5e44332612e8bd28fbeed842e3cd75bf4f1
# BUILD_DATE=20230403
# BUILD_TAG=2023-04-03
# STATUS=completed
# VERSION=latest01
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-03
begin = 2023-04-03 12:02:41.967918321+00:00
start-sync_0 = 12:03:51
start-zstd = 12:04:03
start-sync_1 = 12:04:21
end-sync_1 = 12:04:31
end = 2023-04-03 12:04:31.260540605+00:00

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
nginx = '1.23.4'
njs = '0.7.11'
pkg_release = '1'
```
