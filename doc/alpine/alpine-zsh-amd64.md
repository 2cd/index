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
tag = ["zsh", "2022-07-21"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_amd64_2022-07-21_00-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "9132e419e3ae623ac27c560e03a69c0cb6b4c21ab505c43533f6accebca096ba"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "95M"
tar_bytes = 99106816

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "28M"
zstd_bytes = 29067043

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220714"
previous_tag = "2022-07-14"
previous_file = "alpine-zsh_amd64_2022-07-14_00-04-rootfs.tar.zst"
previous_sha256 = "0d0b2e5b255f8389f65ed78560452ec0b400962caa265ce67d3685b889b39c98"

current_version = "latest02"
current_date = "20220721"
old_file = "alpine-zsh_amd64_2022-07-07_00-05-rootfs.tar.zst"
old_sha256 = "aa4471dec34c4378c8761a54adb5f90f5f639f5579104ae47b32b6e1794d501e"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-zsh_amd64_2022-07-21_00-05-rootfs.tar.zst
# SHA256SUM=9132e419e3ae623ac27c560e03a69c0cb6b4c21ab505c43533f6accebca096ba
# BUILD_DATE=20220721
# BUILD_TAG=2022-07-21
# STATUS=completed
# VERSION=latest02
# END_TIME=00:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-21
begin = 2022-07-21 00:02:26.300967360+00:00
start-sync_0 = 00:02:58
start-zstd = 00:04:21
start-sync_1 = 00:04:56
end-sync_1 = 00:05:04
end = 2022-07-21 00:05:04.425748563+00:00

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
ldd = 'musl libc (x86_64) Version 1.2.3'
zsh = 'zsh 5.9 (x86_64-alpine-linux-musl)'
```
