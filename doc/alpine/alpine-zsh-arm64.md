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
tag = ["zsh", "2023-01-19"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_arm64_2023-01-19_00-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d77add821929c20a935bc96251e37da4efcbbe965165cc1d527487f4bcb1b5aa"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "107M"
tar_bytes = 111151616

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "29M"
zstd_bytes = 30206282

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230112"
previous_tag = "2023-01-12"
previous_file = "alpine-zsh_arm64_2023-01-12_00-06-rootfs.tar.zst"
previous_sha256 = "337000d63ac73f06d5fcd91c06d8ff9f9d776db8f194d214df9bf50fb5406e7a"

current_version = "latest01"
current_date = "20230119"
old_file = "alpine-zsh_arm64_2023-01-05_00-06-rootfs.tar.zst"
old_sha256 = "5f7d411a8e37f85eab294877018dc3d5079e36e59753a8c5ac2b3d29b0a9bd07"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-zsh_arm64_2023-01-19_00-06-rootfs.tar.zst
# SHA256SUM=d77add821929c20a935bc96251e37da4efcbbe965165cc1d527487f4bcb1b5aa
# BUILD_DATE=20230119
# BUILD_TAG=2023-01-19
# STATUS=completed
# VERSION=latest01
# END_TIME=00:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-19
begin = 2023-01-19 00:02:32.557949944+00:00
start-sync_0 = 00:04:31
start-zstd = 00:05:56
start-sync_1 = 00:06:31
end-sync_1 = 00:06:41
end = 2023-01-19 00:06:41.927652820+00:00

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
