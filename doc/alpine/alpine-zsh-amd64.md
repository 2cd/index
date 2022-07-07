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
tag = ["zsh", "2022-07-07"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_amd64_2022-07-07_00-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "aa4471dec34c4378c8761a54adb5f90f5f639f5579104ae47b32b6e1794d501e"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "95M"
tar_bytes = 99027456

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "28M"
zstd_bytes = 29044054

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220630"
previous_tag = "2022-06-30"
previous_file = "alpine-zsh_amd64_2022-06-30_00-05-rootfs.tar.zst"
previous_sha256 = "2fd49e62c9409724307c4d4e1909b57d28a708840f3da64135dd9eaef89a7342"

current_version = "latest02"
current_date = "20220707"
old_file = "alpine-zsh_amd64_2022-06-23_00-05-rootfs.tar.zst"
old_sha256 = "0d76991155e4bd6d10b6f50c1aed4c97beda9ef3f241ad7eb364fd05cc0b93b2"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-zsh_amd64_2022-07-07_00-05-rootfs.tar.zst
# SHA256SUM=aa4471dec34c4378c8761a54adb5f90f5f639f5579104ae47b32b6e1794d501e
# BUILD_DATE=20220707
# BUILD_TAG=2022-07-07
# STATUS=completed
# VERSION=latest02
# END_TIME=00:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-07
begin = 2022-07-07 00:02:31.011729985+00:00
start-sync_0 = 00:03:07
start-zstd = 00:04:32
start-sync_1 = 00:05:09
end-sync_1 = 00:05:19
end = 2022-07-07 00:05:19.429891837+00:00

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
