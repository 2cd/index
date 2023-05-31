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
tag = ["zsh", "2023-05-31"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_armhf_2023-05-31_12-24.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "641157403207e641635265532fe20913ba9fae2176008a31ecd74db1a5a096d1"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "705M"
tar_bytes = 738733056

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "144M"
zstd_bytes = 150000644

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230524"
previous_tag = "2023-05-24"
previous_file = "debian-zsh_armhf_2023-05-24_12-20-rootfs.tar.zst"
previous_sha256 = "c48e892d8fe0fd214610f6b928d6ec077452cbe4becdf036f4f9e3e35b7f16ea"

current_version = "latest01"
current_date = "20230531"
old_file = "debian-zsh_armhf_2023-05-17_12-23-rootfs.tar.zst"
old_sha256 = "3ffb9c24fadfe106f8159a44f201b2e0e17f3328efcef3ba804c08a693a10835"
# edition 2021
# DISTRO_NAME=debian-sid_armhf
# ROOTFS_FILE=debian-zsh_armhf_2023-05-31_12-24-rootfs.tar.zst
# SHA256SUM=641157403207e641635265532fe20913ba9fae2176008a31ecd74db1a5a096d1
# BUILD_DATE=20230531
# BUILD_TAG=2023-05-31
# STATUS=completed
# VERSION=latest01
# END_TIME=12:24

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-05-31
begin = 2023-05-31 12:02:46.380051443+00:00
start-sync_0 = 12:19:08
start-zstd = 12:21:04
start-sync_1 = 12:23:45
end-sync_1 = 12:24:04
end = 2023-05-31 12:24:04.279650249+00:00

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
