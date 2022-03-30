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
tag = ["zsh", "2022-03-30"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "alpine-zsh_amd64_2022-03-30_23-04.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "bf4d76c2978dfcbf9105f39d915ea91e40acd80643d82fb3ba12206256fcc624"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "93M"
tar_bytes = 97511936

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "27M"
zstd_bytes = 28094503

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220324"
previous_tag = "2022-03-24"
previous_file = "alpine-zsh_amd64_2022-03-24_00-05-rootfs.tar.zst"
previous_sha256 = "3a88b45734c06283179a776cde161bcf5fefa6547347136c04e2f34fc96c445a"

current_version = "latest01"
current_date = "20220330"
old_file = "alpine-zsh_amd64_2022-03-17_00-04-rootfs.tar.zst"
old_sha256 = "f19d049959b2279307ff5d0d450af01c4a9314195ef68889aa5b8b1a787a61ad"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-zsh_amd64_2022-03-30_23-04-rootfs.tar.zst
# SHA256SUM=bf4d76c2978dfcbf9105f39d915ea91e40acd80643d82fb3ba12206256fcc624
# BUILD_DATE=20220330
# BUILD_TAG=2022-03-30
# STATUS=completed
# VERSION=latest01
# END_TIME=23:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-30
begin = 2022-03-30 23:02:21.908982241+00:00
start-sync_0 = 23:02:48
start-zstd = 23:04:11
start-sync_1 = 23:04:44
end-sync_1 = 23:04:50
end = 2022-03-30 23:04:50.232321026+00:00

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
