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
tag = ["zsh", "2022-07-07"]
os = "alpine"
release = "edge"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_i386_2022-07-07_00-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "6779a1f5ccb1116eabaae339dfdb5fc7242af2a4915b9869ba876d8fa7cf4e7f"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "97M"
tar_bytes = 100856320

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "29M"
zstd_bytes = 30014155

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220630"
previous_tag = "2022-06-30"
previous_file = "alpine-zsh_i386_2022-06-30_00-06-rootfs.tar.zst"
previous_sha256 = "ff1de0681f388beaee1cbfe020f7fe135712892b2ad0478b07ded912bdfcf42a"

current_version = "latest02"
current_date = "20220707"
old_file = "alpine-zsh_i386_2022-06-23_00-06-rootfs.tar.zst"
old_sha256 = "a745df3f211104e70797e15707d2c3e2971eaa1852ce0993f98b5f14a9b4094f"
# edition 2021
# DISTRO_NAME=alpine-edge_i386
# ROOTFS_FILE=alpine-zsh_i386_2022-07-07_00-05-rootfs.tar.zst
# SHA256SUM=6779a1f5ccb1116eabaae339dfdb5fc7242af2a4915b9869ba876d8fa7cf4e7f
# BUILD_DATE=20220707
# BUILD_TAG=2022-07-07
# STATUS=completed
# VERSION=latest02
# END_TIME=00:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-07
begin = 2022-07-07 00:02:24.984650612+00:00
start-sync_0 = 00:03:33
start-zstd = 00:04:55
start-sync_1 = 00:05:22
end-sync_1 = 00:05:29
end = 2022-07-07 00:05:29.305812864+00:00

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
