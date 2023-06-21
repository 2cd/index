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
tag = ["zsh", "2023-06-21"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_armhf_2023-06-21_12-18.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "234c033699138bf82fe4de517f9f15a8192f8c27bdede34e71ceecda0509f027"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "703M"
tar_bytes = 737046016

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "144M"
zstd_bytes = 150269034

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230614"
previous_tag = "2023-06-14"
previous_file = "debian-zsh_armhf_2023-06-14_12-18-rootfs.tar.zst"
previous_sha256 = "3911beb1f2c40497646c30b2856978779d7337d850fcefdbf396d027b9a8903c"

current_version = "latest02"
current_date = "20230621"
old_file = "debian-zsh_armhf_2023-06-07_12-18-rootfs.tar.zst"
old_sha256 = "4d91b5773758487eebb19c666199320e65aa439e2965a29f63dbad58516195e4"
# edition 2021
# DISTRO_NAME=debian-sid_armhf
# ROOTFS_FILE=debian-zsh_armhf_2023-06-21_12-18-rootfs.tar.zst
# SHA256SUM=234c033699138bf82fe4de517f9f15a8192f8c27bdede34e71ceecda0509f027
# BUILD_DATE=20230621
# BUILD_TAG=2023-06-21
# STATUS=completed
# VERSION=latest02
# END_TIME=12:18

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-21
begin = 2023-06-21 12:02:38.534745792+00:00
start-sync_0 = 12:13:55
start-zstd = 12:15:37
start-sync_1 = 12:17:50
end-sync_1 = 12:18:04
end = 2023-06-21 12:18:04.092259151+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-9) 2.36'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabihf)'
```
