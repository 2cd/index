# kali-zsh-armv7

## How to run it?

```sh
docker run \
    -it \
    --name kali-zsh-armv7 \
    cake233/kali-zsh-armv7
```

## How to exec shell?

```sh
docker exec -it kali-zsh-armv7 zsh
```

## kali-zsh-armv7.toml

```toml
[main]
name = "kali"
tag = ["zsh", "2022-02-03"]
os = "kali"
release = "rolling"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "kali-zsh_armhf_2022-02-03_12-17.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "6b50c82eb187beb3428e462aa5922c11dd5db722d8c2052649cd18a28e6c9ecc"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "664M"
tar_bytes = 695814656

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "137M"
zstd_bytes = 142856548

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220127"
previous_tag = "2022-01-27"
previous_file = "kali-zsh_armhf_2022-01-27_12-17-rootfs.tar.zst"
previous_sha256 = "b8d2b45ddefe17405635e8b60cfe6be31bebc52d969f7c194f76cae33384b1c7"

current_version = "latest01"
current_date = "20220203"
old_file = "kali-zsh_armhf_2022-01-20_12-19-rootfs.tar.zst"
old_sha256 = "7b262ace46a4a7ada22dfe6b8cd1797eb7f2c2ed44fde1f04af0b9e34e6e2f82"
# edition 2021
# DISTRO_NAME=kali-rolling_armhf
# ROOTFS_FILE=kali-zsh_armhf_2022-02-03_12-17-rootfs.tar.zst
# SHA256SUM=6b50c82eb187beb3428e462aa5922c11dd5db722d8c2052649cd18a28e6c9ecc
# BUILD_DATE=20220203
# BUILD_TAG=2022-02-03
# STATUS=completed
# VERSION=latest01
# END_TIME=12:17

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-03
begin = 2022-02-03 12:02:33.373683431+00:00
start-sync_0 = 12:13:32
start-zstd = 12:15:18
start-sync_1 = 12:17:29
end-sync_1 = 12:17:45
end = 2022-02-03 12:17:45.257859658+00:00

[server]
repo = "cake233/kali-zsh-armv7"

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
ldd = 'ldd (Debian GLIBC 2.33-1) 2.33'
zsh = 'zsh 5.8 (arm-unknown-linux-gnueabihf)'
```
