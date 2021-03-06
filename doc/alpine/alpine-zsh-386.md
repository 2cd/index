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
tag = ["zsh", "2022-07-21"]
os = "alpine"
release = "edge"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_i386_2022-07-21_00-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8568180d57705d41b67e72e6fb8c932f1cbbb4a3629d76e0bd3428401786eea8"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "97M"
tar_bytes = 100940288

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "29M"
zstd_bytes = 30043794

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220714"
previous_tag = "2022-07-14"
previous_file = "alpine-zsh_i386_2022-07-14_00-06-rootfs.tar.zst"
previous_sha256 = "3a6ce90907846751bcf638a4a1d4e322107023153ceb3022eeb6eda193a56c0e"

current_version = "latest02"
current_date = "20220721"
old_file = "alpine-zsh_i386_2022-07-07_00-05-rootfs.tar.zst"
old_sha256 = "6779a1f5ccb1116eabaae339dfdb5fc7242af2a4915b9869ba876d8fa7cf4e7f"
# edition 2021
# DISTRO_NAME=alpine-edge_i386
# ROOTFS_FILE=alpine-zsh_i386_2022-07-21_00-06-rootfs.tar.zst
# SHA256SUM=8568180d57705d41b67e72e6fb8c932f1cbbb4a3629d76e0bd3428401786eea8
# BUILD_DATE=20220721
# BUILD_TAG=2022-07-21
# STATUS=completed
# VERSION=latest02
# END_TIME=00:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-21
begin = 2022-07-21 00:02:29.521208333+00:00
start-sync_0 = 00:04:11
start-zstd = 00:05:35
start-sync_1 = 00:06:12
end-sync_1 = 00:06:21
end = 2022-07-21 00:06:21.824261691+00:00

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
zsh = 'zsh 5.9 (i586-alpine-linux-musl)'
```
