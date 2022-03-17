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
tag = ["zsh", "2022-03-17"]
os = "kali"
release = "rolling"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "kali-zsh_armhf_2022-03-17_12-19.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "fa053c02785e60b37dd09845b3a7efb779c57aaf5749bc8a56757957a3f87c43"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "667M"
tar_bytes = 698425856

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "137M"
zstd_bytes = 143425893

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220310"
previous_tag = "2022-03-10"
previous_file = "kali-zsh_armhf_2022-03-10_12-20-rootfs.tar.zst"
previous_sha256 = "552f660d4171f1725150f34dea5d80569a5d93156f176fe7a19996e749619272"

current_version = "latest01"
current_date = "20220317"
old_file = "kali-zsh_armhf_2022-03-03_12-17-rootfs.tar.zst"
old_sha256 = "ef3d77c8e6326006680156af7ace8e4184928db53fc12b8dcd963f2f35fbcb95"
# edition 2021
# DISTRO_NAME=kali-rolling_armhf
# ROOTFS_FILE=kali-zsh_armhf_2022-03-17_12-19-rootfs.tar.zst
# SHA256SUM=fa053c02785e60b37dd09845b3a7efb779c57aaf5749bc8a56757957a3f87c43
# BUILD_DATE=20220317
# BUILD_TAG=2022-03-17
# STATUS=completed
# VERSION=latest01
# END_TIME=12:19

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-17
begin = 2022-03-17 12:02:26.640547689+00:00
start-sync_0 = 12:14:54
start-zstd = 12:16:39
start-sync_1 = 12:18:55
end-sync_1 = 12:19:09
end = 2022-03-17 12:19:10.001332637+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-6) 2.33'
zsh = 'zsh 5.8.1 (arm-unknown-linux-gnueabihf)'
```
