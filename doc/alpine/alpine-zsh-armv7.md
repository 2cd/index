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
tag = ["zsh", "2023-02-16"]
os = "alpine"
release = "edge"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_armhf_2023-02-16_00-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "114c26ee7671dfd039f6c67f0f605b953df2f841adab3d1867d33b53304bd6a3"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "81M"
tar_bytes = 84855296

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "30M"
zstd_bytes = 30885327

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230209"
previous_tag = "2023-02-09"
previous_file = "alpine-zsh_armhf_2023-02-09_00-05-rootfs.tar.zst"
previous_sha256 = "eeb8fa08da73167d95e5f0bc710ee8fb244093652dd9aa3214633cbe7097b1d5"

current_version = "latest02"
current_date = "20230216"
old_file = "alpine-zsh_armhf_2023-02-02_00-06-rootfs.tar.zst"
old_sha256 = "6e47b0f66819058018e4a7533d46cb535153f450422a572f8845b39c6a138f48"
# edition 2021
# DISTRO_NAME=alpine-edge_armhf
# ROOTFS_FILE=alpine-zsh_armhf_2023-02-16_00-06-rootfs.tar.zst
# SHA256SUM=114c26ee7671dfd039f6c67f0f605b953df2f841adab3d1867d33b53304bd6a3
# BUILD_DATE=20230216
# BUILD_TAG=2023-02-16
# STATUS=completed
# VERSION=latest02
# END_TIME=00:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-16
begin = 2023-02-16 00:02:26.400650211+00:00
start-sync_0 = 00:04:07
start-zstd = 00:05:31
start-sync_1 = 00:05:52
end-sync_1 = 00:06:02
end = 2023-02-16 00:06:02.527247819+00:00

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
