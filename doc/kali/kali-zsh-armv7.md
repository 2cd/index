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
tag = ["zsh", "2023-04-06"]
os = "kali"
release = "rolling"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_armhf_2023-04-06_12-24.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "83720dd85921e2d0447f9746b5d9189a274f28a3d30564ca8cf5bb64422685fe"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "757M"
tar_bytes = 792956416

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "144M"
zstd_bytes = 150428368

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230330"
previous_tag = "2023-03-30"
previous_file = "kali-zsh_armhf_2023-03-30_12-29-rootfs.tar.zst"
previous_sha256 = "1325e8d09545f0af544831fdf8e5d98907cf718a8867e6cd7602971bfa6f2d5d"

current_version = "latest01"
current_date = "20230406"
old_file = "kali-zsh_armhf_2023-03-23_12-24-rootfs.tar.zst"
old_sha256 = "0e41ca471a6adde321bd3eaabf8ee95ac4b21f3d5ceea9f15f5380305ef8625a"
# edition 2021
# DISTRO_NAME=kali-rolling_armhf
# ROOTFS_FILE=kali-zsh_armhf_2023-04-06_12-24-rootfs.tar.zst
# SHA256SUM=83720dd85921e2d0447f9746b5d9189a274f28a3d30564ca8cf5bb64422685fe
# BUILD_DATE=20230406
# BUILD_TAG=2023-04-06
# STATUS=completed
# VERSION=latest01
# END_TIME=12:24

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-06
begin = 2023-04-06 12:02:26.970265058+00:00
start-sync_0 = 12:20:00
start-zstd = 12:21:46
start-sync_1 = 12:24:10
end-sync_1 = 12:24:23
end = 2023-04-06 12:24:23.417365883+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-8) 2.36'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabi)'
```
