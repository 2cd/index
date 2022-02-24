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
tag = ["zsh", "2022-02-24"]
os = "alpine"
release = "edge"
arch = "i386"
platform = "linux/386"
x11_or_wayland = false

[file]
name = "alpine-zsh_i386_2022-02-24_00-06.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "e23f3ea90e90eb1a5e5da64d353a43f1168fb20aecd97ade204c1e3deea50606"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "95M"
tar_bytes = 99242496

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "28M"
zstd_bytes = 29019848

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220217"
previous_tag = "2022-02-17"
previous_file = "alpine-zsh_i386_2022-02-17_00-05-rootfs.tar.zst"
previous_sha256 = "8fc376498afdae69fcbda558e1655ac14756b01673af16d3443d73e683f8c7ed"

current_version = "latest02"
current_date = "20220224"
old_file = "alpine-zsh_i386_2022-02-10_00-05-rootfs.tar.zst"
old_sha256 = "a3f1f8a6a95cbb42cab9a5ffac44987e7581d46a022b8d274ef7119517512290"
# edition 2021
# DISTRO_NAME=alpine-edge_i386
# ROOTFS_FILE=alpine-zsh_i386_2022-02-24_00-06-rootfs.tar.zst
# SHA256SUM=e23f3ea90e90eb1a5e5da64d353a43f1168fb20aecd97ade204c1e3deea50606
# BUILD_DATE=20220224
# BUILD_TAG=2022-02-24
# STATUS=completed
# VERSION=latest02
# END_TIME=00:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-24
begin = 2022-02-24 00:02:28.780539815+00:00
start-sync_0 = 00:04:04
start-zstd = 00:05:31
start-sync_1 = 00:06:10
end-sync_1 = 00:06:22
end = 2022-02-24 00:06:22.926662133+00:00

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
ldd = 'musl libc (i386) Version 1.2.2'
zsh = 'zsh 5.8.1 (i586-alpine-linux-musl)'
```
