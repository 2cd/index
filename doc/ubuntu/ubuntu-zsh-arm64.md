# ubuntu-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name ubuntu-zsh-arm64 \
    cake233/ubuntu-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it ubuntu-zsh-arm64 zsh
```

## ubuntu-zsh-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["zsh", "2023-10-03", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-zsh_arm64_2023-10-03_00-26.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "3bc8a3ae6dc420701b623bdabe024d4792cb96caf0dc74b910d499fd2235c7de"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "803M"
tar_bytes = 841192448

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "151M"
zstd_bytes = 158305435

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230926"
previous_tag = "2023-09-26"
previous_file = "ubuntu-zsh_arm64_2023-09-26_00-25-rootfs.tar.zst"
previous_sha256 = "b6bd3111a81170fd34c8b821fdc267f994346b767693c66b9421ee8640de358b"

current_version = "latest01"
current_date = "20231003"
old_file = "ubuntu-zsh_arm64_2023-09-19_00-27-rootfs.tar.zst"
old_sha256 = "4db5d2d2ef3ed29c60596bc93912cecf563b533ccecb62dd034f680fd1b25a57"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-zsh_arm64_2023-10-03_00-26-rootfs.tar.zst
# SHA256SUM=3bc8a3ae6dc420701b623bdabe024d4792cb96caf0dc74b910d499fd2235c7de
# BUILD_DATE=20231003
# BUILD_TAG=2023-10-03
# STATUS=completed
# VERSION=latest01
# END_TIME=00:26

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-03
begin = 2023-10-03 00:02:38.449088515+00:00
start-sync_0 = 00:21:28
start-zstd = 00:23:16
start-sync_1 = 00:25:58
end-sync_1 = 00:26:16
end = 2023-10-03 00:26:16.995335372+00:00

[server]
repo = "cake233/ubuntu-zsh-arm64"

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
ldd = 'ldd (Ubuntu GLIBC 2.38-1ubuntu5) 2.38'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'
```
