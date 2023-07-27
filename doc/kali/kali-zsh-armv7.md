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
tag = ["zsh", "2023-07-27"]
os = "kali"
release = "rolling"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_armhf_2023-07-27_12-32.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "3dfbdcaa53f83efd39c4b1edaaeed6ad75156c8b0e835be45c3d5b0367298c18"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "740M"
tar_bytes = 775222784

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "144M"
zstd_bytes = 150200551

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230720"
previous_tag = "2023-07-20"
previous_file = "kali-zsh_armhf_2023-07-20_12-33-rootfs.tar.zst"
previous_sha256 = "29040c4dbcb01a4f78d261cecf49e71558150c0c661f0808b2ddc82f00612b5d"

current_version = "latest01"
current_date = "20230727"
old_file = "kali-zsh_armhf_2023-07-13_12-25-rootfs.tar.zst"
old_sha256 = "4769f0f3629d4b86c2077e4e0b4855d625e1b12d160d75d88f24aaa0c2709e52"
# edition 2021
# DISTRO_NAME=kali-rolling_armhf
# ROOTFS_FILE=kali-zsh_armhf_2023-07-27_12-32-rootfs.tar.zst
# SHA256SUM=3dfbdcaa53f83efd39c4b1edaaeed6ad75156c8b0e835be45c3d5b0367298c18
# BUILD_DATE=20230727
# BUILD_TAG=2023-07-27
# STATUS=completed
# VERSION=latest01
# END_TIME=12:32

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-27
begin = 2023-07-27 12:02:33.513072330+00:00
start-sync_0 = 12:27:20
start-zstd = 12:29:19
start-sync_1 = 12:32:35
end-sync_1 = 12:32:54
end = 2023-07-27 12:32:54.836393735+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-5) 2.37'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabi)'
```
