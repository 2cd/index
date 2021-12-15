# arch-zsh-arm64

## How to run it?

```shell
docker run \
    -it \
    --name arch-zsh-arm64 \
    cake233/arch-zsh-arm64
```

## How to exec shell?

```shell
    docker exec -it arch-zsh-arm64 zsh
```

## arch-zsh-arm64.toml

```toml
[main]
name = "arch"
tag = ["zsh", "2021-12-15"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "arch-zsh_arm64_2021-12-15_00-18.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "8ffb41e9361dd0280805bf078ab2819b57d7c90180eebb66749b5308af5006d6"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "960M"
tar_bytes = 1006135296

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "220M"
zstd_bytes = 230492529

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211212"
previous_tag = "2021-12-12"
previous_file = "arch-zsh_arm64_2021-12-12_05-55-rootfs.tar.zst"
previous_sha256 = "3ce493b88d2de3b08af134b70d58fc3ed8b2185c0d4d905a0a0f0525b3610d0a"

current_version = "latest01"
current_date = "20211215"
old_file = "arch-zsh_arm64_2021-12-08_01-24-rootfs.tar.zst"
old_sha256 = "266a7bc0316f6838d459036463bfe32ed29b34d50b19574e529594ee35deb3c4"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-zsh_arm64_2021-12-15_00-18-rootfs.tar.zst
# SHA256SUM=8ffb41e9361dd0280805bf078ab2819b57d7c90180eebb66749b5308af5006d6
# BUILD_DATE=20211215
# BUILD_TAG=2021-12-15
# STATUS=completed
# VERSION=latest01
# END_TIME=00:18

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-15
begin = 2021-12-15 00:05:41.591811568+00:00
start-sync_0 = 00:12:26
start-zstd = 00:14:08
start-sync_1 = 00:17:56
end-sync_1 = 00:18:18
end = 2021-12-15 00:18:18.127387214+00:00

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
ldd = 'ldd (GNU libc) 2.32'
zsh = 'zsh 5.8 (aarch64-unknown-linux-gnu)'
```
