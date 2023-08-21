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
tag = ["alpine", "2023-08-21", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "nginx-musl_armhf_2023-08-21_12-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b1179cdc855975ca015b6ff9e09979c982fdd4cbcb5acc1b21dbc128a82a3fbf"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "205M"
tar_bytes = 214761472

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "37M"
zstd_bytes = 38094551

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230807"
previous_tag = "2023-08-07"
previous_file = "nginx-musl_armhf_2023-08-07_12-04-rootfs.tar.zst"
previous_sha256 = "92dab3810b9c1ee80a2dd2bec4dfaa3943158a15e926cc0dc597e905878cb715"

current_version = "latest02"
current_date = "20230821"
old_file = "nginx-musl_armhf_2023-07-24_12-03-rootfs.tar.zst"
old_sha256 = "2aabfa23f4f14d66e37132675d86fadb6ee458371911cd998cf368d176e9ed74"
# edition 2021
# DISTRO_NAME=nginx_armhf
# ROOTFS_FILE=nginx-musl_armhf_2023-08-21_12-05-rootfs.tar.zst
# SHA256SUM=b1179cdc855975ca015b6ff9e09979c982fdd4cbcb5acc1b21dbc128a82a3fbf
# BUILD_DATE=20230821
# BUILD_TAG=2023-08-21
# STATUS=completed
# VERSION=latest02
# END_TIME=12:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-21
begin = 2023-08-21 12:02:43.119652809+00:00
start-sync_0 = 12:03:42
start-zstd = 12:03:55
start-sync_1 = 12:05:04
end-sync_1 = 12:05:16
end = 2023-08-21 12:05:16.459728811+00:00

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
ldd = 'musl libc (armhf) Version 1.2.4'
nginx = '1.25.2'
njs = '0.8.0'
pkg_release = '1'
```
