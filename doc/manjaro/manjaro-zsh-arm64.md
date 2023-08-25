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
tag = ["zsh", "2023-08-25"]
os = "manjaro"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-zsh_arm64_2023-08-25_12-20.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f2c215dec9333ec583a6ca89f14da099641949adf2257e29c3c3de321f0d5fe5"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.2G"
tar_bytes = 1201606144

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "258M"
zstd_bytes = 270123172

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230818"
previous_tag = "2023-08-18"
previous_file = "manjaro-zsh_arm64_2023-08-18_12-26-rootfs.tar.zst"
previous_sha256 = "30270c389f32edda7cfc78fb45df8c0e50f7d8a261b394092476490fdfb123fe"

current_version = "latest01"
current_date = "20230825"
old_file = "manjaro-zsh_arm64_2023-08-11_12-20-rootfs.tar.zst"
old_sha256 = "7a914832e64618a7afe70261c7481a118d9d9d0f9c4d0efccf76b7626d22db7a"
# edition 2021
# DISTRO_NAME=manjaro-stable_arm64
# ROOTFS_FILE=manjaro-zsh_arm64_2023-08-25_12-20-rootfs.tar.zst
# SHA256SUM=f2c215dec9333ec583a6ca89f14da099641949adf2257e29c3c3de321f0d5fe5
# BUILD_DATE=20230825
# BUILD_TAG=2023-08-25
# STATUS=completed
# VERSION=latest01
# END_TIME=12:20

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-25
begin = 2023-08-25 12:02:34.005727223+00:00
start-sync_0 = 12:14:15
start-zstd = 12:15:52
start-sync_1 = 12:20:28
end-sync_1 = 12:20:51
end = 2023-08-25 12:20:51.571499223+00:00

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
