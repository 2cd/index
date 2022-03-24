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
tag = ["zsh", "2022-03-24"]
os = "kali"
release = "rolling"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "kali-zsh_armhf_2022-03-24_12-17.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "e53f6e5e2567dc1940f8acc5743009861f5edc195b1fbf5ec87adb70439a3b4b"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "667M"
tar_bytes = 698463232

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "137M"
zstd_bytes = 143386247

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220317"
previous_tag = "2022-03-17"
previous_file = "kali-zsh_armhf_2022-03-17_12-19-rootfs.tar.zst"
previous_sha256 = "fa053c02785e60b37dd09845b3a7efb779c57aaf5749bc8a56757957a3f87c43"

current_version = "latest02"
current_date = "20220324"
old_file = "kali-zsh_armhf_2022-03-10_12-20-rootfs.tar.zst"
old_sha256 = "552f660d4171f1725150f34dea5d80569a5d93156f176fe7a19996e749619272"
# edition 2021
# DISTRO_NAME=kali-rolling_armhf
# ROOTFS_FILE=kali-zsh_armhf_2022-03-24_12-17-rootfs.tar.zst
# SHA256SUM=e53f6e5e2567dc1940f8acc5743009861f5edc195b1fbf5ec87adb70439a3b4b
# BUILD_DATE=20220324
# BUILD_TAG=2022-03-24
# STATUS=completed
# VERSION=latest02
# END_TIME=12:17

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-24
begin = 2022-03-24 12:02:31.839709338+00:00
start-sync_0 = 12:13:07
start-zstd = 12:14:56
start-sync_1 = 12:16:56
end-sync_1 = 12:17:12
end = 2022-03-24 12:17:12.164800157+00:00

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
