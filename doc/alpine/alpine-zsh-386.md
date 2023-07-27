# alpine-zsh-386

## How to run it?

```sh
docker run \
    -it \
    --name alpine-zsh-386 \
    cake233/alpine-zsh-386
```

## How to exec shell?

```sh
docker exec -it alpine-zsh-386 zsh
```

## alpine-zsh-386.toml

```toml
[main]
name = "alpine"
tag = ["zsh", "2023-07-27"]
os = "alpine"
release = "edge"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_i386_2023-07-27_00-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "be1826e2e0b9f7b3054f1bc692bfc53563da567e41ac9626766a20d24fc82dc6"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "122M"
tar_bytes = 127721472

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "37M"
zstd_bytes = 38670767

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230720"
previous_tag = "2023-07-20"
previous_file = "alpine-zsh_i386_2023-07-20_00-05-rootfs.tar.zst"
previous_sha256 = "837636a690615cd47356f8810408726e9d155f15b41e4084179175d4de269c76"

current_version = "latest02"
current_date = "20230727"
old_file = "alpine-zsh_i386_2023-07-13_00-06-rootfs.tar.zst"
old_sha256 = "308933cf6b10661295942fcab67c37652f70c315cd0a33bd72c12d10d0be8726"
# edition 2021
# DISTRO_NAME=alpine-edge_i386
# ROOTFS_FILE=alpine-zsh_i386_2023-07-27_00-06-rootfs.tar.zst
# SHA256SUM=be1826e2e0b9f7b3054f1bc692bfc53563da567e41ac9626766a20d24fc82dc6
# BUILD_DATE=20230727
# BUILD_TAG=2023-07-27
# STATUS=completed
# VERSION=latest02
# END_TIME=00:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-27
begin = 2023-07-27 00:02:30.660573481+00:00
start-sync_0 = 00:03:59
start-zstd = 00:05:22
start-sync_1 = 00:06:04
end-sync_1 = 00:06:17
end = 2023-07-27 00:06:17.987082474+00:00

[server]
repo = "cake233/alpine-zsh-386"

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
ldd = 'musl libc (i386) Version 1.2.4'
zsh = 'zsh 5.9 (i586-alpine-linux-musl)'
```
