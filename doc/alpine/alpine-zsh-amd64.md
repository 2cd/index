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
tag = ["zsh", "2023-03-23"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_amd64_2023-03-23_00-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "dd1966a9a82d589e10d8170e60d4b1b1c2987c408e0981f1329a9cfba5e60551"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "97M"
tar_bytes = 100882432

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "32M"
zstd_bytes = 32526678

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230316"
previous_tag = "2023-03-16"
previous_file = "alpine-zsh_amd64_2023-03-16_00-05-rootfs.tar.zst"
previous_sha256 = "206d67298afd7dc461cbcb2f48cd885f5d27b0a88b5eae9ee0fc26463dd12c8c"

current_version = "latest01"
current_date = "20230323"
old_file = "alpine-zsh_amd64_2023-03-09_00-05-rootfs.tar.zst"
old_sha256 = "f3dcd74049625042984643ec550f6454104750479e9081127e0a3d4e885a7d06"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-zsh_amd64_2023-03-23_00-05-rootfs.tar.zst
# SHA256SUM=dd1966a9a82d589e10d8170e60d4b1b1c2987c408e0981f1329a9cfba5e60551
# BUILD_DATE=20230323
# BUILD_TAG=2023-03-23
# STATUS=completed
# VERSION=latest01
# END_TIME=00:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-23
begin = 2023-03-23 00:02:42.170460645+00:00
start-sync_0 = 00:03:11
start-zstd = 00:04:32
start-sync_1 = 00:05:05
end-sync_1 = 00:05:11
end = 2023-03-23 00:05:11.839765855+00:00

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
