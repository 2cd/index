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
tag = ["zsh", "2022-02-23"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "debian-zsh_arm64_2022-02-23_12-19.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "20cd0173c87d4ce09babbb966eae6890bc57fee4d5c0b8d204d7c9a8124a39a0"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "736M"
tar_bytes = 771253248

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "143M"
zstd_bytes = 149524652

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220216"
previous_tag = "2022-02-16"
previous_file = "debian-zsh_arm64_2022-02-16_12-17-rootfs.tar.zst"
previous_sha256 = "4e35250a682cbbcb9a165c3b23a976393f9d903c94ad788457d6daa4bab25d91"

current_version = "latest02"
current_date = "20220223"
old_file = "debian-zsh_arm64_2022-02-09_12-21-rootfs.tar.zst"
old_sha256 = "84dde442dc334804dcbaa45d5bb90ca46b8a214d25db1937cc12de5bc0ee880e"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-zsh_arm64_2022-02-23_12-19-rootfs.tar.zst
# SHA256SUM=20cd0173c87d4ce09babbb966eae6890bc57fee4d5c0b8d204d7c9a8124a39a0
# BUILD_DATE=20220223
# BUILD_TAG=2022-02-23
# STATUS=completed
# VERSION=latest02
# END_TIME=12:19

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-23
begin = 2022-02-23 12:02:27.825551033+00:00
start-sync_0 = 12:15:06
start-zstd = 12:16:54
start-sync_1 = 12:19:25
end-sync_1 = 12:19:39
end = 2022-02-23 12:19:39.577620744+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-7) 2.33'
zsh = 'zsh 5.8.1 (aarch64-unknown-linux-gnu)'
```
