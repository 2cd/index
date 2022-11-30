# arch-zsh-armv7

## How to run it?

```sh
docker run \
    -it \
    --name arch-zsh-armv7 \
    cake233/arch-zsh-armv7
```

## How to exec shell?

```sh
docker exec -it arch-zsh-armv7 zsh
```

## arch-zsh-armv7.toml

```toml
[main]
name = "arch"
tag = ["zsh", "2022-11-30"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-zsh_armhf_2022-11-30_00-32.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "426cd740e0d1e587fb9e2a881ba6e750204d05ceef26abadad288eea78429a40"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "894M"
tar_bytes = 937181184

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "220M"
zstd_bytes = 230292848

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221123"
previous_tag = "2022-11-23"
previous_file = "arch-zsh_armhf_2022-11-23_00-32-rootfs.tar.zst"
previous_sha256 = "02931f0af0cd6691869e0d78b9534580b6a0d7eb2116f83b2a3c888fbacd3117"

current_version = "latest01"
current_date = "20221130"
old_file = "arch-zsh_armhf_2022-11-20_20-38-rootfs.tar.zst"
old_sha256 = "a81e0c0ee19625edd112aa7d22d4364e0e3b6c59d76d825aacd0838efeb047f8"
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch-zsh_armhf_2022-11-30_00-32-rootfs.tar.zst
# SHA256SUM=426cd740e0d1e587fb9e2a881ba6e750204d05ceef26abadad288eea78429a40
# BUILD_DATE=20221130
# BUILD_TAG=2022-11-30
# STATUS=completed
# VERSION=latest01
# END_TIME=00:32

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-30
begin = 2022-11-30 00:07:49.921899333+00:00
start-sync_0 = 00:26:40
start-zstd = 00:28:13
start-sync_1 = 00:32:16
end-sync_1 = 00:32:39
end = 2022-11-30 00:32:39.898804944+00:00

[server]
repo = "cake233/arch-zsh-armv7"

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
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.9 (armv7l-unknown-linux-gnueabihf)'
```
