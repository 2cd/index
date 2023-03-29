# debian-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name debian-zsh-arm64 \
    cake233/debian-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it debian-zsh-arm64 zsh
```

## debian-zsh-arm64.toml

```toml
[main]
name = "debian"
tag = ["zsh", "2023-03-29"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_arm64_2023-03-29_12-20.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "84e9e33a15f46219430478d20742ef0010898204b04c59e0b1b0e5adde8b1927"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "815M"
tar_bytes = 853822464

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "149M"
zstd_bytes = 155877801

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230322"
previous_tag = "2023-03-22"
previous_file = "debian-zsh_arm64_2023-03-22_12-18-rootfs.tar.zst"
previous_sha256 = "5f4883837d23a1327c0f74fab9b2f6eee14d408bfbba6dd596efca3b55ea6035"

current_version = "latest02"
current_date = "20230329"
old_file = "debian-zsh_arm64_2023-03-15_12-20-rootfs.tar.zst"
old_sha256 = "c9239486ce5b32fcb3e82803755128b55d0fc43d164882483add99181994e312"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-zsh_arm64_2023-03-29_12-20-rootfs.tar.zst
# SHA256SUM=84e9e33a15f46219430478d20742ef0010898204b04c59e0b1b0e5adde8b1927
# BUILD_DATE=20230329
# BUILD_TAG=2023-03-29
# STATUS=completed
# VERSION=latest02
# END_TIME=12:20

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-29
begin = 2023-03-29 12:02:34.067694884+00:00
start-sync_0 = 12:15:37
start-zstd = 12:17:30
start-sync_1 = 12:20:28
end-sync_1 = 12:20:46
end = 2023-03-29 12:20:46.651870253+00:00

[server]
repo = "cake233/debian-zsh-arm64"

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
ldd = 'ldd (Debian GLIBC 2.36-8) 2.36'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'
```
