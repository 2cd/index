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
tag = ["zsh", "2023-05-18"]
os = "kali"
release = "rolling"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_armhf_2023-05-18_12-25.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "05f8a08ef4c000b2038002614bbb93c7d7dbdaf0a37951893131a93871d9cb6c"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "743M"
tar_bytes = 778300416

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "144M"
zstd_bytes = 150357965

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230511"
previous_tag = "2023-05-11"
previous_file = "kali-zsh_armhf_2023-05-11_12-27-rootfs.tar.zst"
previous_sha256 = "f33f366cc41a43b6122d0953dea9af058e89c7cc6b50d9813374a7470bf078b9"

current_version = "latest01"
current_date = "20230518"
old_file = "kali-zsh_armhf_2023-05-04_12-28-rootfs.tar.zst"
old_sha256 = "72d364d6c543aa1fc86de2971e5c2d999c9de0f6ed1212b407f867756e73e193"
# edition 2021
# DISTRO_NAME=kali-rolling_armhf
# ROOTFS_FILE=kali-zsh_armhf_2023-05-18_12-25-rootfs.tar.zst
# SHA256SUM=05f8a08ef4c000b2038002614bbb93c7d7dbdaf0a37951893131a93871d9cb6c
# BUILD_DATE=20230518
# BUILD_TAG=2023-05-18
# STATUS=completed
# VERSION=latest01
# END_TIME=12:25

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-05-18
begin = 2023-05-18 12:02:49.716363455+00:00
start-sync_0 = 12:21:00
start-zstd = 12:22:56
start-sync_1 = 12:25:42
end-sync_1 = 12:25:58
end = 2023-05-18 12:25:58.205045454+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-9) 2.36'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabi)'
```
