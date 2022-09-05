# nginx-alpine-amd64

## How to run it?

```sh
docker run \
    -it \
    --name nginx-alpine-amd64 \
    cake233/nginx-alpine-amd64
```

## How to exec shell?

```sh
docker exec -it nginx-alpine-amd64 bash
```

## nginx-alpine-amd64.toml

```toml
[main]
name = "nginx"
tag = ["alpine", "2022-09-05", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "nginx-musl_amd64_2022-09-05_12-03.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "9636f80fa8ad4fa04ceaa3ab1b90ddc0b27438199246ff8b30e0b3ab1a9e8788"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "35M"
tar_bytes = 36005888

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "9.3M"
zstd_bytes = 9722795

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220822"
previous_tag = "2022-08-22"
previous_file = "nginx-musl_amd64_2022-08-22_12-03-rootfs.tar.zst"
previous_sha256 = "8977e1f8d49585fff43088e8fade6243b718e28cd0218bbc71d8a932ba09b11b"

current_version = "latest02"
current_date = "20220905"
old_file = "nginx-musl_amd64_2022-08-08_12-03-rootfs.tar.zst"
old_sha256 = "0db4b52033451ec2969e47c86df35f74da404320e6a6971c724061c82eb16b1c"
# edition 2021
# DISTRO_NAME=nginx_amd64
# ROOTFS_FILE=nginx-musl_amd64_2022-09-05_12-03-rootfs.tar.zst
# SHA256SUM=9636f80fa8ad4fa04ceaa3ab1b90ddc0b27438199246ff8b30e0b3ab1a9e8788
# BUILD_DATE=20220905
# BUILD_TAG=2022-09-05
# STATUS=completed
# VERSION=latest02
# END_TIME=12:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-05
begin = 2022-09-05 12:02:28.529072841+00:00
start-sync_0 = 12:03:20
start-zstd = 12:03:30
start-sync_1 = 12:03:50
end-sync_1 = 12:03:58
end = 2022-09-05 12:03:58.042205797+00:00

[server]
repo = "cake233/nginx-alpine-amd64"

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
ldd = 'musl libc (x86_64) Version 1.2.3'
nginx = '1.23.1'
njs = '0.7.6'
pkg_release = '1'
```
