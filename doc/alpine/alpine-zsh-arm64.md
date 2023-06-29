# alpine-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name alpine-zsh-arm64 \
    cake233/alpine-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it alpine-zsh-arm64 zsh
```

## alpine-zsh-arm64.toml

```toml
[main]
name = "alpine"
tag = ["zsh", "2023-06-29"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_arm64_2023-06-29_00-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "127c66c4ddec2f1c165a987729f39a53168807eb0ebad81d7ec84def84176f73"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "113M"
tar_bytes = 117731840

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "31M"
zstd_bytes = 32021673

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230622"
previous_tag = "2023-06-22"
previous_file = "alpine-zsh_arm64_2023-06-22_00-05-rootfs.tar.zst"
previous_sha256 = "80fe8635c44fb973365ad66c12fc3064ff17a058ad1b65af0e61921ca5d89d4f"

current_version = "latest02"
current_date = "20230629"
old_file = "alpine-zsh_arm64_2023-06-15_00-06-rootfs.tar.zst"
old_sha256 = "b16bcaf231b99863f56676946c6f9fdf95a1b5fa33459f54698a1b0a533d8b26"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-zsh_arm64_2023-06-29_00-06-rootfs.tar.zst
# SHA256SUM=127c66c4ddec2f1c165a987729f39a53168807eb0ebad81d7ec84def84176f73
# BUILD_DATE=20230629
# BUILD_TAG=2023-06-29
# STATUS=completed
# VERSION=latest02
# END_TIME=00:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-29
begin = 2023-06-29 00:02:34.687705863+00:00
start-sync_0 = 00:04:28
start-zstd = 00:05:54
start-sync_1 = 00:06:35
end-sync_1 = 00:06:46
end = 2023-06-29 00:06:46.912088483+00:00

[server]
repo = "cake233/alpine-zsh-arm64"

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
ldd = 'musl libc (aarch64) Version 1.2.4'
zsh = 'zsh 5.9 (aarch64-alpine-linux-musl)'
```
