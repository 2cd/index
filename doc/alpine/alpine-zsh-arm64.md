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
tag = ["zsh", "2022-01-27"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "alpine-zsh_arm64_2022-01-27_00-06.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "268e02ff27b9db0ba79dee7370435572582f20bbd8319a073af1bdb2eabda8b6"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "94M"
tar_bytes = 97897984

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "27M"
zstd_bytes = 27667436

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220120"
previous_tag = "2022-01-20"
previous_file = "alpine-zsh_arm64_2022-01-20_00-05-rootfs.tar.zst"
previous_sha256 = "7b3bbcb8a15db77174e7dc5a69ca62d3d6348e5bf2e478f5fb5f079153a11750"

current_version = "latest02"
current_date = "20220127"
old_file = "alpine-zsh_arm64_2022-01-06_00-06-rootfs.tar.zst"
old_sha256 = "5a517e8a194ef4c69334569fe19706e00fcd4267e3602ce3497498e31e5eeefd"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-zsh_arm64_2022-01-27_00-06-rootfs.tar.zst
# SHA256SUM=268e02ff27b9db0ba79dee7370435572582f20bbd8319a073af1bdb2eabda8b6
# BUILD_DATE=20220127
# BUILD_TAG=2022-01-27
# STATUS=completed
# VERSION=latest02
# END_TIME=00:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-27
begin = 2022-01-27 00:02:25.857522739+00:00
start-sync_0 = 00:03:55
start-zstd = 00:05:25
start-sync_1 = 00:06:07
end-sync_1 = 00:06:15
end = 2022-01-27 00:06:15.204708007+00:00

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
LANG = "C.UTF-8"

[version]
ldd = 'musl libc (aarch64) Version 1.2.2'
zsh = 'zsh 5.8 (aarch64-alpine-linux-musl)'
```
