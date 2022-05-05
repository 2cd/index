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
tag = ["zsh", "2022-05-05"]
os = "alpine"
release = "edge"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_i386_2022-05-05_00-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "88589f04c6ba1639b5aea6b3ca57b5fa8fb7db38b28d12bb67070516ff99a710"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "96M"
tar_bytes = 99788800

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "28M"
zstd_bytes = 29140686

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220428"
previous_tag = "2022-04-28"
previous_file = "alpine-zsh_i386_2022-04-28_00-06-rootfs.tar.zst"
previous_sha256 = "1d63be02b0d342bdb3478431f545d25b08710153937557c81ba2bb527659ff4e"

current_version = "latest01"
current_date = "20220505"
old_file = "alpine-zsh_i386_2022-04-21_00-05-rootfs.tar.zst"
old_sha256 = "f98d3475ed90b4808ed5db900b3ddd61e9093a0f5697cb9e9c0c70ebf4d7cd64"
# edition 2021
# DISTRO_NAME=alpine-edge_i386
# ROOTFS_FILE=alpine-zsh_i386_2022-05-05_00-06-rootfs.tar.zst
# SHA256SUM=88589f04c6ba1639b5aea6b3ca57b5fa8fb7db38b28d12bb67070516ff99a710
# BUILD_DATE=20220505
# BUILD_TAG=2022-05-05
# STATUS=completed
# VERSION=latest01
# END_TIME=00:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-05
begin = 2022-05-05 00:02:31.884053403+00:00
start-sync_0 = 00:03:57
start-zstd = 00:05:18
start-sync_1 = 00:05:55
end-sync_1 = 00:06:01
end = 2022-05-05 00:06:01.501254387+00:00

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
ldd = 'musl libc (i386) Version 1.2.3'
zsh = 'zsh 5.8.1 (i586-alpine-linux-musl)'
```
