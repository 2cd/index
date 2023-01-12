# kali-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name kali-zsh-arm64 \
    cake233/kali-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it kali-zsh-arm64 zsh
```

## kali-zsh-arm64.toml

```toml
[main]
name = "kali"
tag = ["zsh", "2023-01-12"]
os = "kali"
release = "rolling"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_arm64_2023-01-12_12-22.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "49d0867a2adf0a8bbf9ad8245f2d71ba6be4c99a7c0ba0953d5c1d6a141ca263"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "805M"
tar_bytes = 843998720

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "146M"
zstd_bytes = 152651806

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230105"
previous_tag = "2023-01-05"
previous_file = "kali-zsh_arm64_2023-01-05_12-18-rootfs.tar.zst"
previous_sha256 = "b8a052696283d12bfa464c60f49c8d63f11540c08c7d58037dfa24d5ef5ee016"

current_version = "latest02"
current_date = "20230112"
old_file = "kali-zsh_arm64_2022-12-29_12-17-rootfs.tar.zst"
old_sha256 = "430af53e90949bc87fbca8f062bd2720850dacbb9bc9ee83f3e7e623976fd9a3"
# edition 2021
# DISTRO_NAME=kali-rolling_arm64
# ROOTFS_FILE=kali-zsh_arm64_2023-01-12_12-22-rootfs.tar.zst
# SHA256SUM=49d0867a2adf0a8bbf9ad8245f2d71ba6be4c99a7c0ba0953d5c1d6a141ca263
# BUILD_DATE=20230112
# BUILD_TAG=2023-01-12
# STATUS=completed
# VERSION=latest02
# END_TIME=12:22

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-12
begin = 2023-01-12 12:02:27.975792638+00:00
start-sync_0 = 12:18:03
start-zstd = 12:19:47
start-sync_1 = 12:22:10
end-sync_1 = 12:22:22
end = 2023-01-12 12:22:22.703295932+00:00

[server]
repo = "cake233/kali-zsh-arm64"

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
LANG = "en_US.UTF-8"

[version]
ldd = 'ldd (Debian GLIBC 2.36-6) 2.36'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'
```
