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
tag = ["zsh", "2023-11-09"]
os = "alpine"
release = "edge"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_i386_2023-11-09_00-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "775134fdb6eb0b1ea92d9fc691f917c1446c6f6757718e738cab0de8c97632c6"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "124M"
tar_bytes = 129321472

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "38M"
zstd_bytes = 39393021

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231026"
previous_tag = "2023-10-26"
previous_file = "alpine-zsh_i386_2023-10-26_00-07-rootfs.tar.zst"
previous_sha256 = "a4a2e3c161a7cbb0a49551dd14b3045e2f734cab4b7496d470b09448ee2c9685"

current_version = "latest01"
current_date = "20231109"
old_file = "alpine-zsh_i386_2023-10-19_00-06-rootfs.tar.zst"
old_sha256 = "85725a1f847998902486058da6af7e4b00561a594f94eb4f5213ae87dbb468cb"
# edition 2021
# DISTRO_NAME=alpine-edge_i386
# ROOTFS_FILE=alpine-zsh_i386_2023-11-09_00-06-rootfs.tar.zst
# SHA256SUM=775134fdb6eb0b1ea92d9fc691f917c1446c6f6757718e738cab0de8c97632c6
# BUILD_DATE=20231109
# BUILD_TAG=2023-11-09
# STATUS=completed
# VERSION=latest01
# END_TIME=00:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-11-09
begin = 2023-11-09 00:02:28.510589248+00:00
start-sync_0 = 00:04:27
start-zstd = 00:05:49
start-sync_1 = 00:06:35
end-sync_1 = 00:06:43
end = 2023-11-09 00:06:43.538375808+00:00

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
ldd = 'musl libc (i386) Version 1.2.4_git20230717'
zsh = 'zsh 5.9 (i586-alpine-linux-musl)'
```
