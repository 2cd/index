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
tag = ["zsh", "2022-09-07"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_armhf_2022-09-07_12-17.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ee804cb763c8fb4e658ab1948dff8aa8f8c5ad4e52dfc4d14c7000f204b8c8bd"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "718M"
tar_bytes = 752123904

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "141M"
zstd_bytes = 147548064

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220831"
previous_tag = "2022-08-31"
previous_file = "debian-zsh_armhf_2022-08-31_12-17-rootfs.tar.zst"
previous_sha256 = "48a38167a2fdb2994e5d2004ba5c4d4aa0d6e9b5aa9ad4a55e82a9a7da3f12f2"

current_version = "latest01"
current_date = "20220907"
old_file = "debian-zsh_armhf_2022-08-24_12-16-rootfs.tar.zst"
old_sha256 = "80fc9d03623860c42907f2b7f890c3ee835a8182270a992461d30e92393b7a7e"
# edition 2021
# DISTRO_NAME=debian-sid_armhf
# ROOTFS_FILE=debian-zsh_armhf_2022-09-07_12-17-rootfs.tar.zst
# SHA256SUM=ee804cb763c8fb4e658ab1948dff8aa8f8c5ad4e52dfc4d14c7000f204b8c8bd
# BUILD_DATE=20220907
# BUILD_TAG=2022-09-07
# STATUS=completed
# VERSION=latest01
# END_TIME=12:17

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-07
begin = 2022-09-07 12:02:22.029781495+00:00
start-sync_0 = 12:13:23
start-zstd = 12:15:06
start-sync_1 = 12:17:05
end-sync_1 = 12:17:19
end = 2022-09-07 12:17:19.462538011+00:00

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
ldd = 'ldd (Debian GLIBC 2.34-7) 2.34'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabihf)'
```
