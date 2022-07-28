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
tag = ["zsh", "2022-07-28"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_arm64_2022-07-28_00-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ec6ebbcc8d7d2eb36a49e11cb508726070ad7c68280c42e92ea53ab7c34be835"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "96M"
tar_bytes = 100063232

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "28M"
zstd_bytes = 28980928

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220714"
previous_tag = "2022-07-14"
previous_file = "alpine-zsh_arm64_2022-07-14_00-05-rootfs.tar.zst"
previous_sha256 = "4e7d1e0c885a7851a07be82473eb8e737e0e8cff401315bf8bf485159fdbc35a"

current_version = "latest02"
current_date = "20220728"
old_file = "alpine-zsh_arm64_2022-07-07_00-06-rootfs.tar.zst"
old_sha256 = "64b078249ce415c0f2d3021cba77516cb7d364dec9017338d7abea2addd68ba7"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-zsh_arm64_2022-07-28_00-06-rootfs.tar.zst
# SHA256SUM=ec6ebbcc8d7d2eb36a49e11cb508726070ad7c68280c42e92ea53ab7c34be835
# BUILD_DATE=20220728
# BUILD_TAG=2022-07-28
# STATUS=completed
# VERSION=latest02
# END_TIME=00:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-28
begin = 2022-07-28 00:02:32.669920696+00:00
start-sync_0 = 00:04:01
start-zstd = 00:05:28
start-sync_1 = 00:05:59
end-sync_1 = 00:06:11
end = 2022-07-28 00:06:11.393486465+00:00

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
ldd = 'musl libc (aarch64) Version 1.2.3'
zsh = 'zsh 5.9 (aarch64-alpine-linux-musl)'
```
