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
tag = ["zsh", "2022-04-28"]
os = "alpine"
release = "edge"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_i386_2022-04-28_00-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "1d63be02b0d342bdb3478431f545d25b08710153937557c81ba2bb527659ff4e"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "96M"
tar_bytes = 99782144

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "28M"
zstd_bytes = 29141065

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220421"
previous_tag = "2022-04-21"
previous_file = "alpine-zsh_i386_2022-04-21_00-05-rootfs.tar.zst"
previous_sha256 = "f98d3475ed90b4808ed5db900b3ddd61e9093a0f5697cb9e9c0c70ebf4d7cd64"

current_version = "latest02"
current_date = "20220428"
old_file = "alpine-zsh_i386_2022-04-14_00-06-rootfs.tar.zst"
old_sha256 = "08d516507c8890a2f0dd52acf0d7adda82854656dc6e4365c86276ee1619bf43"
# edition 2021
# DISTRO_NAME=alpine-edge_i386
# ROOTFS_FILE=alpine-zsh_i386_2022-04-28_00-06-rootfs.tar.zst
# SHA256SUM=1d63be02b0d342bdb3478431f545d25b08710153937557c81ba2bb527659ff4e
# BUILD_DATE=20220428
# BUILD_TAG=2022-04-28
# STATUS=completed
# VERSION=latest02
# END_TIME=00:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-28
begin = 2022-04-28 00:02:35.853906377+00:00
start-sync_0 = 00:04:05
start-zstd = 00:05:27
start-sync_1 = 00:06:01
end-sync_1 = 00:06:07
end = 2022-04-28 00:06:07.993740940+00:00

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
