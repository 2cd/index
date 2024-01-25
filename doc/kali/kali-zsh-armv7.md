# kali-zsh-armv7

## How to run it?

```sh
docker run \
    -it \
    --name kali-zsh-armv7 \
    cake233/kali-zsh-armv7
```

## How to exec shell?

```sh
docker exec -it kali-zsh-armv7 zsh
```

## kali-zsh-armv7.toml

```toml
[main]
name = "kali"
tag = ["zsh", "2024-01-25"]
os = "kali"
release = "rolling"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_armhf_2024-01-25_12-18.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ddf699597fd44a0e71d8d4caca56aa9d9d52f53f440c68045e6d51c1d7bd0a90"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "744M"
tar_bytes = 779945984

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "149M"
zstd_bytes = 155530593

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231123"
previous_tag = "2023-11-23"
previous_file = "kali-zsh_armhf_2023-11-23_12-19-rootfs.tar.zst"
previous_sha256 = "f413bac83d6a2e8e7e79f560f31d006f573624519f2a66a89ecfbe9cc806183a"

current_version = "latest02"
current_date = "20240125"
old_file = "kali-zsh_armhf_2023-11-16_12-19-rootfs.tar.zst"
old_sha256 = "ce02bb4e96db2557d35e76d6658c9906578a3a83ee8183a60dea0620dd694d03"
# edition 2021
# DISTRO_NAME=kali-rolling_armhf
# ROOTFS_FILE=kali-zsh_armhf_2024-01-25_12-18-rootfs.tar.zst
# SHA256SUM=ddf699597fd44a0e71d8d4caca56aa9d9d52f53f440c68045e6d51c1d7bd0a90
# BUILD_DATE=20240125
# BUILD_TAG=2024-01-25
# STATUS=completed
# VERSION=latest02
# END_TIME=12:18

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-01-25
begin = 2024-01-25 12:02:33.365786431+00:00
start-sync_0 = 12:14:33
start-zstd = 12:16:10
start-sync_1 = 12:18:18
end-sync_1 = 12:18:33
end = 2024-01-25 12:18:33.904687200+00:00

[server]
repo = "cake233/kali-zsh-armv7"

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
ldd = 'ldd (Debian GLIBC 2.37-12) 2.37'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabi)'
```
