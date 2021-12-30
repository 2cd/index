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
tag = ["zsh", "2021-12-30"]
os = "alpine"
release = "edge"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "alpine-zsh_armhf_2021-12-30_00-05.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "05625103a38f7106be6e70b6f3ceaf082e80091e980cbfe00498688f857e75a4"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "74M"
tar_bytes = 77212672

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "26M"
zstd_bytes = 26255899

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211223"
previous_tag = "2021-12-23"
previous_file = "alpine-zsh_armhf_2021-12-23_00-05-rootfs.tar.zst"
previous_sha256 = "0b8098968c6f6252746e69f92a235225465a61ab874d63e4c189acfaef0525ec"

current_version = "latest02"
current_date = "20211230"
old_file = "alpine-zsh_armhf_2021-12-16_00-06-rootfs.tar.zst"
old_sha256 = "a40dea3e8258d1dbae4c57f89c246efbeddd6859061745c3e61903faf9060100"
# edition 2021
# DISTRO_NAME=alpine-edge_armhf
# ROOTFS_FILE=alpine-zsh_armhf_2021-12-30_00-05-rootfs.tar.zst
# SHA256SUM=05625103a38f7106be6e70b6f3ceaf082e80091e980cbfe00498688f857e75a4
# BUILD_DATE=20211230
# BUILD_TAG=2021-12-30
# STATUS=completed
# VERSION=latest02
# END_TIME=00:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-30
begin = 2021-12-30 00:02:24.775667935+00:00
start-sync_0 = 00:03:55
start-zstd = 00:05:22
start-sync_1 = 00:05:44
end-sync_1 = 00:05:55
end = 2021-12-30 00:05:55.515480760+00:00

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
LANG = "C.UTF-8"

[version]
ldd = 'musl libc (armhf) Version 1.2.2'
zsh = 'zsh 5.8 (armv7-alpine-linux-musleabihf)'
```
