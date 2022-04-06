# alpine-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name alpine-zsh-arm64 \
    cake233/alpine-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it alpine-zsh-arm64 zsh
```

## alpine-zsh-arm64.toml

```toml
[main]
name = "alpine"
tag = ["zsh", "2022-04-06"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "alpine-zsh_arm64_2022-04-06_23-05.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "ecc32e538b64a0fbf79f3d9266026993b19927fceb2b95f6631754f12a9b235c"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "95M"
tar_bytes = 98959872

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "27M"
zstd_bytes = 28041065

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220330"
previous_tag = "2022-03-30"
previous_file = "alpine-zsh_arm64_2022-03-30_23-05-rootfs.tar.zst"
previous_sha256 = "e290f9c9c564fb976041ec984a8c3badc7068eee566c82297e83e646fedb20d5"

current_version = "latest02"
current_date = "20220406"
old_file = "alpine-zsh_arm64_2022-03-24_00-05-rootfs.tar.zst"
old_sha256 = "0cf6d682665dd5301eca12da9e81f0fd6c0f6550e0e23308a4f3d4d08a2d8344"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-zsh_arm64_2022-04-06_23-05-rootfs.tar.zst
# SHA256SUM=ecc32e538b64a0fbf79f3d9266026993b19927fceb2b95f6631754f12a9b235c
# BUILD_DATE=20220406
# BUILD_TAG=2022-04-06
# STATUS=completed
# VERSION=latest02
# END_TIME=23:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-06
begin = 2022-04-06 23:02:25.971738807+00:00
start-sync_0 = 23:03:48
start-zstd = 23:05:12
start-sync_1 = 23:05:48
end-sync_1 = 23:05:54
end = 2022-04-06 23:05:54.748881696+00:00

[server]
repo = "cake233/alpine-zsh-arm64"

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
ldd = 'musl libc (aarch64) Version 1.2.2'
zsh = 'zsh 5.8.1 (aarch64-alpine-linux-musl)'
```
