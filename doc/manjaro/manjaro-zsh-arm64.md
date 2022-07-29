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
tag = ["zsh", "2022-07-29"]
os = "manjaro"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-zsh_arm64_2022-07-29_12-15.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d8c8d41feb2d39e14451d67a5102988d2895da7cbe7ffc630352c496a80ff008"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1177711104

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "250M"
zstd_bytes = 261314907

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220715"
previous_tag = "2022-07-15"
previous_file = "manjaro-zsh_arm64_2022-07-15_12-17-rootfs.tar.zst"
previous_sha256 = "0786def0414759c08a2383c1bb1b55d8c9df4e02e57ee16debc27588b56fcaed"

current_version = "latest01"
current_date = "20220729"
old_file = "manjaro-zsh_arm64_2022-07-08_12-16-rootfs.tar.zst"
old_sha256 = "8e4028853fe5dca9f4fc61adec86f6b91fa743e5de87b04181a06284572ce8de"
# edition 2021
# DISTRO_NAME=manjaro-stable_arm64
# ROOTFS_FILE=manjaro-zsh_arm64_2022-07-29_12-15-rootfs.tar.zst
# SHA256SUM=d8c8d41feb2d39e14451d67a5102988d2895da7cbe7ffc630352c496a80ff008
# BUILD_DATE=20220729
# BUILD_TAG=2022-07-29
# STATUS=completed
# VERSION=latest01
# END_TIME=12:15

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-29
begin = 2022-07-29 12:02:33.729721741+00:00
start-sync_0 = 12:09:39
start-zstd = 12:11:13
start-sync_1 = 12:15:26
end-sync_1 = 12:15:49
end = 2022-07-29 12:15:49.076441647+00:00

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
