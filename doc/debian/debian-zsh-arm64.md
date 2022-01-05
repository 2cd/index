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
tag = ["zsh", "2022-01-05"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "debian-zsh_arm64_2022-01-05_12-21.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "52dbfe0c806c55635c313e8217c6ef80e056ab8ee913ca4714631fc47f501617"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "726M"
tar_bytes = 761235968

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "141M"
zstd_bytes = 147101853

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211229"
previous_tag = "2021-12-29"
previous_file = "debian-zsh_arm64_2021-12-29_12-23-rootfs.tar.zst"
previous_sha256 = "4d1b62660b5df35e7736d929ca9a2a8eb14be78d60d4ce93fa3c0297ac0b650b"

current_version = "latest02"
current_date = "20220105"
old_file = "debian-zsh_arm64_2021-12-22_12-22-rootfs.tar.zst"
old_sha256 = "e0dd1b45804fae334bfd7fead895b0aa041399965c62fb23816f07475de98558"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-zsh_arm64_2022-01-05_12-21-rootfs.tar.zst
# SHA256SUM=52dbfe0c806c55635c313e8217c6ef80e056ab8ee913ca4714631fc47f501617
# BUILD_DATE=20220105
# BUILD_TAG=2022-01-05
# STATUS=completed
# VERSION=latest02
# END_TIME=12:21

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-05
begin = 2022-01-05 12:02:28.375425987+00:00
start-sync_0 = 12:16:56
start-zstd = 12:18:52
start-sync_1 = 12:21:35
end-sync_1 = 12:21:52
end = 2022-01-05 12:21:52.491416219+00:00

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
LANG = "en_US.UTF-8"

[version]
ldd = 'ldd (Debian GLIBC 2.33-1) 2.33'
zsh = 'zsh 5.8 (aarch64-unknown-linux-gnu)'
```
