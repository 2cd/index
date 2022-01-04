# fedora-zsh-armv7

## How to run it?

```sh
docker run \
    -it \
    --name fedora-zsh-armv7 \
    cake233/fedora-zsh-armv7
```

## How to exec shell?

```sh
docker exec -it fedora-zsh-armv7 zsh
```

## fedora-zsh-armv7.toml

```toml
[main]
name = "fedora"
tag = ["zsh", "2022-01-04"]
os = "fedora"
release = "rawhide"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "fedora-zsh_armhf_2022-01-04_12-16.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "7bc5bf4beada18b3a35a2b328e0fac5f68e46c7427225873a0756e96fa41649d"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "896M"
tar_bytes = 938612736

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "153M"
zstd_bytes = 159804154

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211228"
previous_tag = "2021-12-28"
previous_file = "fedora-zsh_armhf_2021-12-28_12-17-rootfs.tar.zst"
previous_sha256 = "8e1e6259b9907b086270fe4600c1c344c3ec6b80339b7275531e9d3b0dd293d7"

current_version = "latest01"
current_date = "20220104"
old_file = "fedora-zsh_armhf_2021-12-21_12-18-rootfs.tar.zst"
old_sha256 = "db02aafd95df742e2225811ce1d3a55aaf5d03726eb082a68d47e4e01098b0dc"
# edition 2021
# DISTRO_NAME=fedora-rawhide_armhf
# ROOTFS_FILE=fedora-zsh_armhf_2022-01-04_12-16-rootfs.tar.zst
# SHA256SUM=7bc5bf4beada18b3a35a2b328e0fac5f68e46c7427225873a0756e96fa41649d
# BUILD_DATE=20220104
# BUILD_TAG=2022-01-04
# STATUS=completed
# VERSION=latest01
# END_TIME=12:16

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-04
begin = 2022-01-04 12:02:27.669795574+00:00
start-sync_0 = 12:11:29
start-zstd = 12:13:23
start-sync_1 = 12:16:06
end-sync_1 = 12:16:22
end = 2022-01-04 12:16:22.607042390+00:00

[server]
repo = "cake233/fedora-zsh-armv7"

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
ldd = 'ldd (GNU libc) 2.34.9000'
zsh = 'zsh 5.8 (armv7hl-redhat-linux-gnu)'
```
