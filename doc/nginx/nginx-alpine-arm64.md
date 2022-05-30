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
tag = ["alpine", "2022-05-30", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "nginx-musl_arm64_2022-05-30_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "3a1a82ce8f4a5ce2a9dcf71a4f920fb3a0dcc3416e898aaaa33528dedf68e93f"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "33M"
tar_bytes = 34189312

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "9.0M"
zstd_bytes = 9396395

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220516"
previous_tag = "2022-05-16"
previous_file = "nginx-musl_arm64_2022-05-16_12-04-rootfs.tar.zst"
previous_sha256 = "ddbe9173364c1b6ed4decf6c53d5e14b73eb2f8476af90a56c1eaa74ffd52dc1"

current_version = "latest02"
current_date = "20220530"
old_file = "nginx-musl_arm64_2022-05-02_12-03-rootfs.tar.zst"
old_sha256 = "4ee936846534adfb97a3ec95623f296cc4bce5a2b308a66ad06ff2a02e215bee"
# edition 2021
# DISTRO_NAME=nginx_arm64
# ROOTFS_FILE=nginx-musl_arm64_2022-05-30_12-04-rootfs.tar.zst
# SHA256SUM=3a1a82ce8f4a5ce2a9dcf71a4f920fb3a0dcc3416e898aaaa33528dedf68e93f
# BUILD_DATE=20220530
# BUILD_TAG=2022-05-30
# STATUS=completed
# VERSION=latest02
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-30
begin = 2022-05-30 12:02:44.546323521+00:00
start-sync_0 = 12:03:31
start-zstd = 12:03:41
start-sync_1 = 12:03:57
end-sync_1 = 12:04:05
end = 2022-05-30 12:04:05.732934620+00:00

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
ldd = 'musl libc (aarch64) Version 1.2.2'
nginx = '1.21.6'
njs = '0.7.3'
pkg_release = '1'
```
