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
tag = ["zsh", "2021-12-30"]
os = "alpine"
release = "edge"
arch = "i386"
platform = "linux/386"
x11_or_wayland = false

[file]
name = "alpine-zsh_i386_2021-12-30_00-05.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "228b76d91bb70e6082a78db2438106e6d7824df9a1e355a4f989dca5e4733add"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "94M"
tar_bytes = 98165760

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "28M"
zstd_bytes = 28605591

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211223"
previous_tag = "2021-12-23"
previous_file = "alpine-zsh_i386_2021-12-23_00-05-rootfs.tar.zst"
previous_sha256 = "5bdb5ebaf2d68a6e5678ae4705cb127e0b454fd1bb763c679ab0014c813229da"

current_version = "latest01"
current_date = "20211230"
old_file = "alpine-zsh_i386_2021-12-16_00-05-rootfs.tar.zst"
old_sha256 = "f4187015aeb3fcebb7b1973bffffa712fd7876dba38d42f06d0cf6f6fba4231f"
# edition 2021
# DISTRO_NAME=alpine-edge_i386
# ROOTFS_FILE=alpine-zsh_i386_2021-12-30_00-05-rootfs.tar.zst
# SHA256SUM=228b76d91bb70e6082a78db2438106e6d7824df9a1e355a4f989dca5e4733add
# BUILD_DATE=20211230
# BUILD_TAG=2021-12-30
# STATUS=completed
# VERSION=latest01
# END_TIME=00:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-30
begin = 2021-12-30 00:02:24.353369800+00:00
start-sync_0 = 00:03:46
start-zstd = 00:05:10
start-sync_1 = 00:05:42
end-sync_1 = 00:05:51
end = 2021-12-30 00:05:51.354604023+00:00

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
zsh = 'zsh 5.8 (i586-alpine-linux-musl)'
```
