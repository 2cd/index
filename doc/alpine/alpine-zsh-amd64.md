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
tag = ["zsh", "2022-04-14"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false
syntax_version = "0.0.0-alpha.3"

[file]
name = "alpine-zsh_amd64_2022-04-14_00-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "e25941ddee6ed98c5e5c6095b777a111e9d1db77fa7de9d41eb9ac9c4fef30cf"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "94M"
tar_bytes = 97841152

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "27M"
zstd_bytes = 28117295

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220410"
previous_tag = "2022-04-10"
previous_file = "alpine-zsh_amd64_2022-04-10_08-55-rootfs.tar.zst"
previous_sha256 = "d29f378a479ccb5bcea603350b7d0c6a3d2df9c56702201ec1251a8182373683"

current_version = "latest02"
current_date = "20220414"
old_file = "alpine-zsh_amd64_2022-04-06_23-05-rootfs.tar.zst"
old_sha256 = "c25807c8331923d087a8df0fc5090e4a99737cb99305d5e27ea5d9291894bc49"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-zsh_amd64_2022-04-14_00-04-rootfs.tar.zst
# SHA256SUM=e25941ddee6ed98c5e5c6095b777a111e9d1db77fa7de9d41eb9ac9c4fef30cf
# BUILD_DATE=20220414
# BUILD_TAG=2022-04-14
# STATUS=completed
# VERSION=latest02
# END_TIME=00:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-14
begin = 2022-04-14 00:02:24.834180955+00:00
start-sync_0 = 00:02:57
start-zstd = 00:04:19
start-sync_1 = 00:04:53
end-sync_1 = 00:04:59
end = 2022-04-14 00:04:59.344724088+00:00

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
ldd = 'musl libc (x86_64) Version 1.2.3'
zsh = 'zsh 5.8.1 (x86_64-alpine-linux-musl)'
```
