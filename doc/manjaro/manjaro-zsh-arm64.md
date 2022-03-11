# manjaro-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name manjaro-zsh-arm64 \
    cake233/manjaro-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it manjaro-zsh-arm64 zsh
```

## manjaro-zsh-arm64.toml

```toml
[main]
name = "manjaro"
tag = ["zsh", "2022-03-11"]
os = "manjaro"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "manjaro-zsh_arm64_2022-03-11_12-16.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "a68fd06990824d069485e5dd734a1f53386625ae6f913e07d0b73901fbdefbeb"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1169352192

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "247M"
zstd_bytes = 258180195

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220304"
previous_tag = "2022-03-04"
previous_file = "manjaro-zsh_arm64_2022-03-04_12-14-rootfs.tar.zst"
previous_sha256 = "59c70ea20ff49e7e783c318e760102bd6cec030d4b030f575bd3bbae3490abe7"

current_version = "latest02"
current_date = "20220311"
old_file = "manjaro-zsh_arm64_2022-02-25_12-17-rootfs.tar.zst"
old_sha256 = "362fec78c5987c6451a0d26d299b52b88d22fcefec2d6f6f7d1202d7c97afa0c"
# edition 2021
# DISTRO_NAME=manjaro-stable_arm64
# ROOTFS_FILE=manjaro-zsh_arm64_2022-03-11_12-16-rootfs.tar.zst
# SHA256SUM=a68fd06990824d069485e5dd734a1f53386625ae6f913e07d0b73901fbdefbeb
# BUILD_DATE=20220311
# BUILD_TAG=2022-03-11
# STATUS=completed
# VERSION=latest02
# END_TIME=12:16

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-11
begin = 2022-03-11 12:02:30.442766427+00:00
start-sync_0 = 12:09:21
start-zstd = 12:10:54
start-sync_1 = 12:15:34
end-sync_1 = 12:16:00
end = 2022-03-11 12:16:00.649217277+00:00

[server]
repo = "cake233/manjaro-zsh-arm64"

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
