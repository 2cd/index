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
tag = ["zsh", "2022-10-13"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_arm64_2022-10-13_00-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ef28103050b58723163150ae5e5a05b917be6fb7510e65e250ddf5450a0d5495"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "99M"
tar_bytes = 103532032

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "29M"
zstd_bytes = 29911322

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221006"
previous_tag = "2022-10-06"
previous_file = "alpine-zsh_arm64_2022-10-06_00-05-rootfs.tar.zst"
previous_sha256 = "9b2cf43a434792f7589c68762d47f08fb22532b86c78a8d0eed6f047cd9a64a1"

current_version = "latest02"
current_date = "20221013"
old_file = "alpine-zsh_arm64_2022-09-29_00-06-rootfs.tar.zst"
old_sha256 = "83ada22ae6978a160ee48b30c937b91ecb614c33bafbfad3cf08dc704bd47f8f"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-zsh_arm64_2022-10-13_00-05-rootfs.tar.zst
# SHA256SUM=ef28103050b58723163150ae5e5a05b917be6fb7510e65e250ddf5450a0d5495
# BUILD_DATE=20221013
# BUILD_TAG=2022-10-13
# STATUS=completed
# VERSION=latest02
# END_TIME=00:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-13
begin = 2022-10-13 00:02:24.841520163+00:00
start-sync_0 = 00:04:00
start-zstd = 00:05:21
start-sync_1 = 00:05:53
end-sync_1 = 00:05:59
end = 2022-10-13 00:05:59.448735676+00:00

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
ldd = 'musl libc (aarch64) Version 1.2.3'
zsh = 'zsh 5.9 (aarch64-alpine-linux-musl)'
```
