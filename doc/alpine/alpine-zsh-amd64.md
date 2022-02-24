# alpine-zsh-amd64

## How to run it?

```sh
docker run \
    -it \
    --name alpine-zsh-amd64 \
    cake233/alpine-zsh-amd64
```

## How to exec shell?

```sh
docker exec -it alpine-zsh-amd64 zsh
```

## alpine-zsh-amd64.toml

```toml
[main]
name = "alpine"
tag = ["zsh", "2022-02-24"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "alpine-zsh_amd64_2022-02-24_00-04.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "e340f073f8ce9a5a573c04e8acc093b6709bf09c9f9c6e1e5115d9e5e3cc4831"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "94M"
tar_bytes = 97782272

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "27M"
zstd_bytes = 28128097

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220217"
previous_tag = "2022-02-17"
previous_file = "alpine-zsh_amd64_2022-02-17_00-05-rootfs.tar.zst"
previous_sha256 = "8c477ac9e2b8ebcd68dd1ed7f26fd8223e85e457017a3e0a3cabae2b41cd1e89"

current_version = "latest02"
current_date = "20220224"
old_file = "alpine-zsh_amd64_2022-02-10_00-05-rootfs.tar.zst"
old_sha256 = "e66ebe7450c36bd8e83e15160b489c4a514b011cf202d6e39accb6b108c19144"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-zsh_amd64_2022-02-24_00-04-rootfs.tar.zst
# SHA256SUM=e340f073f8ce9a5a573c04e8acc093b6709bf09c9f9c6e1e5115d9e5e3cc4831
# BUILD_DATE=20220224
# BUILD_TAG=2022-02-24
# STATUS=completed
# VERSION=latest02
# END_TIME=00:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-24
begin = 2022-02-24 00:02:24.548054171+00:00
start-sync_0 = 00:02:53
start-zstd = 00:04:13
start-sync_1 = 00:04:43
end-sync_1 = 00:04:49
end = 2022-02-24 00:04:49.332967636+00:00

[server]
repo = "cake233/alpine-zsh-amd64"

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
ldd = 'musl libc (x86_64) Version 1.2.2'
zsh = 'zsh 5.8.1 (x86_64-alpine-linux-musl)'
```
