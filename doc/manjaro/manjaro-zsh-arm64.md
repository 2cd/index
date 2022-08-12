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
tag = ["zsh", "2022-08-12"]
os = "manjaro"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-zsh_arm64_2022-08-12_12-28.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ff11d143c747aef267a3d2a6cd400cd04ade26f7da4ee2230b0bc6132bc76cbf"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1180386816

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "251M"
zstd_bytes = 262679355

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220805"
previous_tag = "2022-08-05"
previous_file = "manjaro-zsh_arm64_2022-08-05_12-25-rootfs.tar.zst"
previous_sha256 = "de9b50c48643dc080f0ec4b3fceccca1cee272a2c4df7c48b30ca278ff9d76bf"

current_version = "latest02"
current_date = "20220812"
old_file = "manjaro-zsh_arm64_2022-07-15_12-17-rootfs.tar.zst"
old_sha256 = "0786def0414759c08a2383c1bb1b55d8c9df4e02e57ee16debc27588b56fcaed"
# edition 2021
# DISTRO_NAME=manjaro-stable_arm64
# ROOTFS_FILE=manjaro-zsh_arm64_2022-08-12_12-28-rootfs.tar.zst
# SHA256SUM=ff11d143c747aef267a3d2a6cd400cd04ade26f7da4ee2230b0bc6132bc76cbf
# BUILD_DATE=20220812
# BUILD_TAG=2022-08-12
# STATUS=completed
# VERSION=latest02
# END_TIME=12:28

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-12
begin = 2022-08-12 12:02:27.264800165+00:00
start-sync_0 = 12:20:56
start-zstd = 12:22:36
start-sync_1 = 12:27:59
end-sync_1 = 12:28:26
end = 2022-08-12 12:28:26.032410540+00:00

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
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'
```
