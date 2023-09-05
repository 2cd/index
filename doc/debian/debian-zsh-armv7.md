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
tag = ["zsh", "2023-08-30"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_armhf_2023-08-30_12-18.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b05bad75f347abb612b1bbdca00216f0fa844a28b7bda0f3e46625c31271f82d"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "740M"
tar_bytes = 775445504

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "156M"
zstd_bytes = 163226346

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20230830"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=debian-sid_armhf
# ROOTFS_FILE=debian-zsh_armhf_2023-08-30_12-18-rootfs.tar.zst
# SHA256SUM=b05bad75f347abb612b1bbdca00216f0fa844a28b7bda0f3e46625c31271f82d
# BUILD_DATE=20230830
# BUILD_TAG=2023-08-30
# STATUS=completed
# VERSION=latest01
# END_TIME=12:18

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-30
begin = 2023-08-30 12:02:41.323289589+00:00
start-sync_0 = 12:14:30
start-zstd = 12:16:11
start-sync_1 = 12:18:32
end-sync_1 = 12:18:50
end = 2023-08-30 12:18:50.878557883+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-7) 2.37'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabihf)'
```