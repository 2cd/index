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
tag = ["zsh", "2022-06-16"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_arm64_2022-06-16_00-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c5bb08a42070f4ced7c4ff91aa366f8e3cb7422c823e1566cb32febbb29150e2"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "95M"
tar_bytes = 99532288

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "28M"
zstd_bytes = 28881875

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220609"
previous_tag = "2022-06-09"
previous_file = "alpine-zsh_arm64_2022-06-09_00-06-rootfs.tar.zst"
previous_sha256 = "f373b63e40dc1511db6365a9c006a500d6ebc781b3ff1a04997cdb9f9ccba508"

current_version = "latest01"
current_date = "20220616"
old_file = "alpine-zsh_arm64_2022-06-02_00-06-rootfs.tar.zst"
old_sha256 = "506999549183c4748ec7b8521649d60a72545ab1f6b8592c594562692ebe9de3"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-zsh_arm64_2022-06-16_00-05-rootfs.tar.zst
# SHA256SUM=c5bb08a42070f4ced7c4ff91aa366f8e3cb7422c823e1566cb32febbb29150e2
# BUILD_DATE=20220616
# BUILD_TAG=2022-06-16
# STATUS=completed
# VERSION=latest01
# END_TIME=00:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-16
begin = 2022-06-16 00:02:30.156076095+00:00
start-sync_0 = 00:03:51
start-zstd = 00:05:16
start-sync_1 = 00:05:48
end-sync_1 = 00:05:58
end = 2022-06-16 00:05:58.326060837+00:00

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
ldd = 'musl libc (aarch64) Version 1.2.3'
zsh = 'zsh 5.8.1 (aarch64-alpine-linux-musl)'
```
