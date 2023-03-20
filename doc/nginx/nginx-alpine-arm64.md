# nginx-alpine-arm64

## How to run it?

```sh
docker run \
    -it \
    --name nginx-alpine-arm64 \
    cake233/nginx-alpine-arm64
```

## How to exec shell?

```sh
docker exec -it nginx-alpine-arm64 bash
```

## nginx-alpine-arm64.toml

```toml
[main]
name = "nginx"
tag = ["alpine", "2023-03-20", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "nginx-musl_arm64_2023-03-20_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c1fa5df111c72bc130bbc6dc10a018df7daa4dd060420e495ba717b7676dd5d9"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "58M"
tar_bytes = 60348928

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "14M"
zstd_bytes = 14071305

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230306"
previous_tag = "2023-03-06"
previous_file = "nginx-musl_arm64_2023-03-06_12-03-rootfs.tar.zst"
previous_sha256 = "0f5819b4eebcd48eb2ebdec6b97cfc5a2e7cc87ca68d8561cffe9ae3385762db"

current_version = "latest02"
current_date = "20230320"
old_file = "nginx-musl_arm64_2023-02-20_12-04-rootfs.tar.zst"
old_sha256 = "c3a4e00ef174b175aea30059fea21a171f8f2c000bd2e3f82328a4bd2a8bf6f9"
# edition 2021
# DISTRO_NAME=nginx_arm64
# ROOTFS_FILE=nginx-musl_arm64_2023-03-20_12-04-rootfs.tar.zst
# SHA256SUM=c1fa5df111c72bc130bbc6dc10a018df7daa4dd060420e495ba717b7676dd5d9
# BUILD_DATE=20230320
# BUILD_TAG=2023-03-20
# STATUS=completed
# VERSION=latest02
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-20
begin = 2023-03-20 12:02:38.375430713+00:00
start-sync_0 = 12:03:25
start-zstd = 12:03:31
start-sync_1 = 12:03:55
end-sync_1 = 12:04:01
end = 2023-03-20 12:04:01.387384041+00:00

[server]
repo = "cake233/nginx-alpine-arm64"

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
ldd = 'musl libc (aarch64) Version 1.2.3'
nginx = '1.23.3'
njs = '0.7.9'
pkg_release = '1'
```
