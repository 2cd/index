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
tag = ["zsh", "2023-11-30"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_arm64_2023-11-30_00-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "6dfd4fb613fea0a7a1f7227c75131593b8d0310f1c8e971302665ac530bd2fdf"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "152M"
tar_bytes = 158841856

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "38M"
zstd_bytes = 39548754

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231123"
previous_tag = "2023-11-23"
previous_file = "alpine-zsh_arm64_2023-11-23_00-06-rootfs.tar.zst"
previous_sha256 = "5cd8cbcd7bac6aa871fc01bf0e06c6dcc1e4afda98a82e146be0cc143c0a709b"

current_version = "latest02"
current_date = "20231130"
old_file = "alpine-zsh_arm64_2023-11-16_00-05-rootfs.tar.zst"
old_sha256 = "98fe7fabb532e9399a30a4dcaf3e4e9e3ea84bc0666aa56c5c5720add56902ea"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-zsh_arm64_2023-11-30_00-05-rootfs.tar.zst
# SHA256SUM=6dfd4fb613fea0a7a1f7227c75131593b8d0310f1c8e971302665ac530bd2fdf
# BUILD_DATE=20231130
# BUILD_TAG=2023-11-30
# STATUS=completed
# VERSION=latest02
# END_TIME=00:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-11-30
begin = 2023-11-30 00:02:28.812857796+00:00
start-sync_0 = 00:03:45
start-zstd = 00:05:07
start-sync_1 = 00:05:39
end-sync_1 = 00:05:46
end = 2023-11-30 00:05:46.601416563+00:00

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
