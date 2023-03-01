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
tag = ["zsh", "2023-03-01"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_armhf_2023-03-01_12-16.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5f63e46387ef7e9320b62e5bcce319965c5eca3b023c121d921a64079c073e6a"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "719M"
tar_bytes = 753849856

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "143M"
zstd_bytes = 149892332

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230222"
previous_tag = "2023-02-22"
previous_file = "debian-zsh_armhf_2023-02-22_12-20-rootfs.tar.zst"
previous_sha256 = "b229a11e7349979e879b529860cf3d896edb45f75de07ae2a84c34594b47378b"

current_version = "latest02"
current_date = "20230301"
old_file = "debian-zsh_armhf_2023-02-15_12-17-rootfs.tar.zst"
old_sha256 = "fea9affd4c2031024eff1a9a4c8e8899d453fc73a3828b5169d78528d4b118b2"
# edition 2021
# DISTRO_NAME=debian-sid_armhf
# ROOTFS_FILE=debian-zsh_armhf_2023-03-01_12-16-rootfs.tar.zst
# SHA256SUM=5f63e46387ef7e9320b62e5bcce319965c5eca3b023c121d921a64079c073e6a
# BUILD_DATE=20230301
# BUILD_TAG=2023-03-01
# STATUS=completed
# VERSION=latest02
# END_TIME=12:16

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-01
begin = 2023-03-01 12:02:27.077814498+00:00
start-sync_0 = 12:12:50
start-zstd = 12:14:35
start-sync_1 = 12:16:39
end-sync_1 = 12:16:54
end = 2023-03-01 12:16:54.720544461+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-8) 2.36'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabihf)'
```
