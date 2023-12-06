# debian-zsh-armv7

## How to run it?

```sh
docker run \
    -it \
    --name debian-zsh-armv7 \
    cake233/debian-zsh-armv7
```

## How to exec shell?

```sh
docker exec -it debian-zsh-armv7 zsh
```

## debian-zsh-armv7.toml

```toml
[main]
name = "debian"
tag = ["zsh", "2023-12-06"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_armhf_2023-12-06_12-16.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "9549223b9345344596a2aeed78d2bf0ddcda492a73700f03ed6fea2f9a8054c0"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "702M"
tar_bytes = 735853568

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "146M"
zstd_bytes = 152313456

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231122"
previous_tag = "2023-11-22"
previous_file = "debian-zsh_armhf_2023-11-22_12-14-rootfs.tar.zst"
previous_sha256 = "48dacd6f29c18ae3b335cf36bd15e9030bddac18a4a4f0822f5c9e047df18f66"

current_version = "latest01"
current_date = "20231206"
old_file = "debian-zsh_armhf_2023-11-15_12-14-rootfs.tar.zst"
old_sha256 = "b7b560fd26058e3333762504bd31dceeb1bf06770a74ac0f8bec2a1bef1de3ee"
# edition 2021
# DISTRO_NAME=debian-sid_armhf
# ROOTFS_FILE=debian-zsh_armhf_2023-12-06_12-16-rootfs.tar.zst
# SHA256SUM=9549223b9345344596a2aeed78d2bf0ddcda492a73700f03ed6fea2f9a8054c0
# BUILD_DATE=20231206
# BUILD_TAG=2023-12-06
# STATUS=completed
# VERSION=latest01
# END_TIME=12:16

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-12-06
begin = 2023-12-06 12:02:37.778262185+00:00
start-sync_0 = 12:12:34
start-zstd = 12:14:15
start-sync_1 = 12:16:00
end-sync_1 = 12:16:16
end = 2023-12-06 12:16:16.522363106+00:00

[server]
repo = "cake233/debian-zsh-armv7"

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
ldd = 'ldd (Debian GLIBC 2.37-13) 2.37'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabihf)'
```
