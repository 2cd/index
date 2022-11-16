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
tag = ["zsh", "2022-11-16"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_armhf_2022-11-16_12-21.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a11d1ab5376e5a9621b53eaacab73da7d2f569132ac44e149ff7daf7a78253d4"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "732M"
tar_bytes = 767458304

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "141M"
zstd_bytes = 147112034

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221109"
previous_tag = "2022-11-09"
previous_file = "debian-zsh_armhf_2022-11-09_12-17-rootfs.tar.zst"
previous_sha256 = "70824d260bcc4096b612d2dca982a213ff97da308a19a59e688f160be694236e"

current_version = "latest01"
current_date = "20221116"
old_file = "debian-zsh_armhf_2022-11-02_12-17-rootfs.tar.zst"
old_sha256 = "2541a7b1b88ca54b292c971c47044cebad5a8cdf7661dc2b6199b5ff86d809d3"
# edition 2021
# DISTRO_NAME=debian-sid_armhf
# ROOTFS_FILE=debian-zsh_armhf_2022-11-16_12-21-rootfs.tar.zst
# SHA256SUM=a11d1ab5376e5a9621b53eaacab73da7d2f569132ac44e149ff7daf7a78253d4
# BUILD_DATE=20221116
# BUILD_TAG=2022-11-16
# STATUS=completed
# VERSION=latest01
# END_TIME=12:21

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-16
begin = 2022-11-16 12:02:26.307923568+00:00
start-sync_0 = 12:16:34
start-zstd = 12:18:26
start-sync_1 = 12:20:55
end-sync_1 = 12:21:13
end = 2022-11-16 12:21:13.495125060+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-5) 2.36'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabihf)'
```
