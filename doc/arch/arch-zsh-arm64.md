# arch-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name arch-zsh-arm64 \
    cake233/arch-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it arch-zsh-arm64 zsh
```

## arch-zsh-arm64.toml

```toml
[main]
name = "arch"
tag = ["zsh", "2022-04-05"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "arch-zsh_arm64_2022-04-05_23-24.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "48972294a4214e8f4002a668406267faa68ad028007fbcd327b2a776bcb6c19a"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "958M"
tar_bytes = 1003581440

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "225M"
zstd_bytes = 235767053

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220329"
previous_tag = "2022-03-29"
previous_file = "arch-zsh_arm64_2022-03-29_23-23-rootfs.tar.zst"
previous_sha256 = "becd32dcf02317bd6537d1a4a626f72d378576e2da5411e896fa68587f4052c6"

current_version = "latest02"
current_date = "20220405"
old_file = "arch-zsh_arm64_2022-03-23_00-28-rootfs.tar.zst"
old_sha256 = "1687d11a2c5098d3712baa12d046d3a3391b5d7a6e8f868e1774c5549dd41b8b"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-zsh_arm64_2022-04-05_23-24-rootfs.tar.zst
# SHA256SUM=48972294a4214e8f4002a668406267faa68ad028007fbcd327b2a776bcb6c19a
# BUILD_DATE=20220405
# BUILD_TAG=2022-04-05
# STATUS=completed
# VERSION=latest02
# END_TIME=23:24

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-05
begin = 2022-04-05 23:05:51.607407005+00:00
start-sync_0 = 23:18:22
start-zstd = 23:20:01
start-sync_1 = 23:23:41
end-sync_1 = 23:24:00
end = 2022-04-05 23:24:00.452792621+00:00

[server]
repo = "cake233/arch-zsh-arm64"

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
LANG = "en_US.UTF-8"

[version]
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.8.1 (aarch64-unknown-linux-gnu)'
```
