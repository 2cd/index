# debian-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name debian-zsh-arm64 \
    cake233/debian-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it debian-zsh-arm64 zsh
```

## debian-zsh-arm64.toml

```toml
[main]
name = "debian"
tag = ["zsh", "2023-09-06"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_arm64_2023-09-06_12-22.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "73d855066b7048b07e6b834a261c15f3d3b94661538d92911101c0dd9d23c276"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "859M"
tar_bytes = 900386304

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "162M"
zstd_bytes = 169439468

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230830"
previous_tag = "2023-08-30"
previous_file = "debian-zsh_arm64_2023-08-30_12-24-rootfs.tar.zst"
previous_sha256 = "05e2ba5a9b45a8437ad05380b72765745bba4a088f1bc8207a3aadfd8d2856c7"

current_version = "latest02"
current_date = "20230906"
old_file = "debian-zsh_arm64_2023-08-16_12-18-rootfs.tar.zst"
old_sha256 = "3268002a42f4f686cb835a98cfe7532d93f9d9ffd526b9a767eaaa723fb3ebb6"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-zsh_arm64_2023-09-06_12-22-rootfs.tar.zst
# SHA256SUM=73d855066b7048b07e6b834a261c15f3d3b94661538d92911101c0dd9d23c276
# BUILD_DATE=20230906
# BUILD_TAG=2023-09-06
# STATUS=completed
# VERSION=latest02
# END_TIME=12:22

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-06
begin = 2023-09-06 12:02:44.268905191+00:00
start-sync_0 = 12:16:53
start-zstd = 12:18:45
start-sync_1 = 12:21:51
end-sync_1 = 12:22:13
end = 2023-09-06 12:22:13.638650447+00:00

[server]
repo = "cake233/debian-zsh-arm64"

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
LANG = "en_US.UTF-8"

[version]
ldd = 'ldd (Debian GLIBC 2.37-7) 2.37'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'
```
