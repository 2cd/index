# arch-zsh-amd64

## How to run it?

```sh
docker run \
    -it \
    --name arch-zsh-amd64 \
    cake233/arch-zsh-amd64
```

## How to exec shell?

```sh
docker exec -it arch-zsh-amd64 zsh
```

## arch-zsh-amd64.toml

```toml
[main]
name = "arch"
tag = ["zsh", "2023-07-05"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-zsh_amd64_2023-07-05_00-16.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b1201d3d59ba9449dcfe9c0ebbb187e46ab0dacc45aaeabb145d2b2006911cf9"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1161874432

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "278M"
zstd_bytes = 291197764

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230628"
previous_tag = "2023-06-28"
previous_file = "arch-zsh_amd64_2023-06-28_00-19-rootfs.tar.zst"
previous_sha256 = "8e98ca833cb56b13a7bfc6590aa067d2c74b364b57623bbf68efd9b3f17bb779"

current_version = "latest01"
current_date = "20230705"
old_file = "arch-zsh_amd64_2023-06-21_00-19-rootfs.tar.zst"
old_sha256 = "9e4514f3c3c5b0f4c238c33b0d6dfad6bf4e3c51bea543f1171ea7be9d22a745"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-zsh_amd64_2023-07-05_00-16-rootfs.tar.zst
# SHA256SUM=b1201d3d59ba9449dcfe9c0ebbb187e46ab0dacc45aaeabb145d2b2006911cf9
# BUILD_DATE=20230705
# BUILD_TAG=2023-07-05
# STATUS=completed
# VERSION=latest01
# END_TIME=00:16

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-05
begin = 2023-07-05 00:07:22.603815501+00:00
start-sync_0 = 00:10:18
start-zstd = 00:11:50
start-sync_1 = 00:16:15
end-sync_1 = 00:16:38
end = 2023-07-05 00:16:38.789355118+00:00

[server]
repo = "cake233/arch-zsh-amd64"

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
ldd = 'ldd (GNU libc) 2.37'
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'
```
