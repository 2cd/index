# alpine-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name alpine-zsh-arm64 \
    cake233/alpine-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it alpine-zsh-arm64 zsh
```

## alpine-zsh-arm64.toml

```toml
[main]
name = "alpine"
tag = ["zsh", "2023-10-05"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_arm64_2023-10-05_00-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a1c51f9aa4a163d21a0b889b7779f77f96de89436754cd1f74460cb3e7390d24"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "151M"
tar_bytes = 157569536

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "38M"
zstd_bytes = 38990139

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230928"
previous_tag = "2023-09-28"
previous_file = "alpine-zsh_arm64_2023-09-28_00-06-rootfs.tar.zst"
previous_sha256 = "e6d1ccd87e6b8e7410ff3ab39ce9c49194753ec23a9d595cfaed0d416760596a"

current_version = "latest01"
current_date = "20231005"
old_file = "alpine-zsh_arm64_2023-09-21_00-07-rootfs.tar.zst"
old_sha256 = "e66519f69958b7fd132c60203bb360ea36699466d7614d0c2657350de827f63f"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-zsh_arm64_2023-10-05_00-07-rootfs.tar.zst
# SHA256SUM=a1c51f9aa4a163d21a0b889b7779f77f96de89436754cd1f74460cb3e7390d24
# BUILD_DATE=20231005
# BUILD_TAG=2023-10-05
# STATUS=completed
# VERSION=latest01
# END_TIME=00:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-05
begin = 2023-10-05 00:03:15.473989458+00:00
start-sync_0 = 00:04:57
start-zstd = 00:06:21
start-sync_1 = 00:07:07
end-sync_1 = 00:07:16
end = 2023-10-05 00:07:16.388407785+00:00

[server]
repo = "cake233/alpine-zsh-arm64"

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
ldd = 'musl libc (aarch64) Version 1.2.4_git20230717'
zsh = 'zsh 5.9 (aarch64-alpine-linux-musl)'
```
