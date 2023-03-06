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
tag = ["alpine", "2023-03-06", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "nginx-musl_armhf_2023-03-06_12-03.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "77768acf5a51584947df9c3d0739376a95c048b362a7bea7fde66808c50af083"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "47M"
tar_bytes = 48380416

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "13M"
zstd_bytes = 12709230

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230220"
previous_tag = "2023-02-20"
previous_file = "nginx-musl_armhf_2023-02-20_12-03-rootfs.tar.zst"
previous_sha256 = "aa1ea540e0617036de4f57f89426f3e8589e02531f4ab7d28efa4f96f96ab60c"

current_version = "latest01"
current_date = "20230306"
old_file = "nginx-musl_armhf_2023-02-06_12-03-rootfs.tar.zst"
old_sha256 = "74c10e30d00d113b4b05ab40e31f3f35c1d589130bd33678c784874be9e0d687"
# edition 2021
# DISTRO_NAME=nginx_armhf
# ROOTFS_FILE=nginx-musl_armhf_2023-03-06_12-03-rootfs.tar.zst
# SHA256SUM=77768acf5a51584947df9c3d0739376a95c048b362a7bea7fde66808c50af083
# BUILD_DATE=20230306
# BUILD_TAG=2023-03-06
# STATUS=completed
# VERSION=latest01
# END_TIME=12:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-06
begin = 2023-03-06 12:02:34.816041568+00:00
start-sync_0 = 12:03:19
start-zstd = 12:03:24
start-sync_1 = 12:03:40
end-sync_1 = 12:03:45
end = 2023-03-06 12:03:45.105718334+00:00

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
nginx = '1.23.3'
njs = '0.7.9'
pkg_release = '1'
```
