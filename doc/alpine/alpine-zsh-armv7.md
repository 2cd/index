# alpine-zsh-armv7

## How to run it?

```sh
docker run \
    -it \
    --name alpine-zsh-armv7 \
    cake233/alpine-zsh-armv7
```

## How to exec shell?

```sh
docker exec -it alpine-zsh-armv7 zsh
```

## alpine-zsh-armv7.toml

```toml
[main]
name = "alpine"
tag = ["zsh", "2022-10-27"]
os = "alpine"
release = "edge"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_armhf_2022-10-27_00-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "6d28cc747ad3445babead32c3d23f2a474bdb72f161772697301ac062d18ebaa"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "80M"
tar_bytes = 83048448

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "28M"
zstd_bytes = 28415979

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221020"
previous_tag = "2022-10-20"
previous_file = "alpine-zsh_armhf_2022-10-20_00-06-rootfs.tar.zst"
previous_sha256 = "9de9c039ce91c9755db463aa9e413e0ed3e618e78b462a15beba5afb5b2544c3"

current_version = "latest01"
current_date = "20221027"
old_file = "alpine-zsh_armhf_2022-10-13_00-06-rootfs.tar.zst"
old_sha256 = "c1224e907fb3f88804eaf98534c1dcffb7139746e2fe37ba37fb93703c36ea92"
# edition 2021
# DISTRO_NAME=alpine-edge_armhf
# ROOTFS_FILE=alpine-zsh_armhf_2022-10-27_00-05-rootfs.tar.zst
# SHA256SUM=6d28cc747ad3445babead32c3d23f2a474bdb72f161772697301ac062d18ebaa
# BUILD_DATE=20221027
# BUILD_TAG=2022-10-27
# STATUS=completed
# VERSION=latest01
# END_TIME=00:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-27
begin = 2022-10-27 00:02:19.049016581+00:00
start-sync_0 = 00:03:50
start-zstd = 00:05:10
start-sync_1 = 00:05:31
end-sync_1 = 00:05:37
end = 2022-10-27 00:05:37.451212763+00:00

[server]
repo = "cake233/alpine-zsh-armv7"

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
LANG = "C.UTF-8"

[version]
ldd = 'musl libc (armhf) Version 1.2.3'
zsh = 'zsh 5.9 (armv7-alpine-linux-musleabihf)'
```
