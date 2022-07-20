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
tag = ["zsh", "2022-07-20"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-zsh_armhf_2022-07-20_00-50.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "9804ad564acea67100befeb533e5bd426bcafdf31e78878c9375a328fe651640"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "855M"
tar_bytes = 895560192

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "210M"
zstd_bytes = 219377764

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220713"
previous_tag = "2022-07-13"
previous_file = "arch-zsh_armhf_2022-07-13_00-32-rootfs.tar.zst"
previous_sha256 = "58b49cf5fb4931eb1ccc76acba35732bfb26931def786c78b309624276eac004"

current_version = "latest01"
current_date = "20220720"
old_file = "arch-zsh_armhf_2022-07-06_00-28-rootfs.tar.zst"
old_sha256 = "3320a83236192ef6fe38ec18e97847f18fabde77dbaa1aa096cab7fac60ece20"
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch-zsh_armhf_2022-07-20_00-50-rootfs.tar.zst
# SHA256SUM=9804ad564acea67100befeb533e5bd426bcafdf31e78878c9375a328fe651640
# BUILD_DATE=20220720
# BUILD_TAG=2022-07-20
# STATUS=completed
# VERSION=latest01
# END_TIME=00:50

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-20
begin = 2022-07-20 00:12:35.705186883+00:00
start-sync_0 = 00:44:26
start-zstd = 00:46:04
start-sync_1 = 00:49:53
end-sync_1 = 00:50:18
end = 2022-07-20 00:50:18.473705807+00:00

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
