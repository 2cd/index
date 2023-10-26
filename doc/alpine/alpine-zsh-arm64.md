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
tag = ["zsh", "2023-10-26"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_arm64_2023-10-26_00-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "9858ad911b8e941ffe1c25c14988d97f5f1a9265c099cc91b6e81fe474857c4d"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "151M"
tar_bytes = 158281216

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "38M"
zstd_bytes = 39313713

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231019"
previous_tag = "2023-10-19"
previous_file = "alpine-zsh_arm64_2023-10-19_00-06-rootfs.tar.zst"
previous_sha256 = "3101261b1ce894761d86a44ac4f2130d8870e08aea6749c4400e89e0a0de5190"

current_version = "latest02"
current_date = "20231026"
old_file = "alpine-zsh_arm64_2023-10-12_00-06-rootfs.tar.zst"
old_sha256 = "e4b75bd38a0fc5a3fcb58dd567aa891f62a64a06eeedd026086abfafe27d7bb9"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-zsh_arm64_2023-10-26_00-07-rootfs.tar.zst
# SHA256SUM=9858ad911b8e941ffe1c25c14988d97f5f1a9265c099cc91b6e81fe474857c4d
# BUILD_DATE=20231026
# BUILD_TAG=2023-10-26
# STATUS=completed
# VERSION=latest02
# END_TIME=00:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-26
begin = 2023-10-26 00:02:36.824157230+00:00
start-sync_0 = 00:04:50
start-zstd = 00:06:18
start-sync_1 = 00:07:04
end-sync_1 = 00:07:14
end = 2023-10-26 00:07:14.609683555+00:00

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
ldd = 'musl libc (aarch64) Version 1.2.4_git20230717'
zsh = 'zsh 5.9 (aarch64-alpine-linux-musl)'
```
