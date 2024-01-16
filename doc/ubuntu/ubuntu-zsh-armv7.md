# ubuntu-zsh-armv7

## How to run it?

```sh
docker run \
    -it \
    --name ubuntu-zsh-armv7 \
    cake233/ubuntu-zsh-armv7
```

## How to exec shell?

```sh
docker exec -it ubuntu-zsh-armv7 zsh
```

## ubuntu-zsh-armv7.toml

```toml
[main]
name = "ubuntu"
tag = ["zsh", "2024-01-16", "devel"]
os = "ubuntu"
release = "dev"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-zsh_armhf_2024-01-16_00-16.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d73fe6e4d4bff357b6cb3791b3e75344d0d061fb7c146b9b99d8284cde04b364"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "666M"
tar_bytes = 697370112

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "140M"
zstd_bytes = 145998065

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231128"
previous_tag = "2023-11-28"
previous_file = "ubuntu-zsh_armhf_2023-11-28_00-16-rootfs.tar.zst"
previous_sha256 = "e6424b90d3625befa50aa85a2a04f2c5031284551bece560b225e2235ab3f09d"

current_version = "latest01"
current_date = "20240116"
old_file = "ubuntu-zsh_armhf_2023-11-21_00-17-rootfs.tar.zst"
old_sha256 = "b4922af5f1f3b7a4521142f7fef67808f663340d03d3db65d1ba56a374d9754b"
# edition 2021
# DISTRO_NAME=ubuntu-dev_armhf
# ROOTFS_FILE=ubuntu-zsh_armhf_2024-01-16_00-16-rootfs.tar.zst
# SHA256SUM=d73fe6e4d4bff357b6cb3791b3e75344d0d061fb7c146b9b99d8284cde04b364
# BUILD_DATE=20240116
# BUILD_TAG=2024-01-16
# STATUS=completed
# VERSION=latest01
# END_TIME=00:16

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-01-16
begin = 2024-01-16 00:02:32.280620974+00:00
start-sync_0 = 00:13:19
start-zstd = 00:14:57
start-sync_1 = 00:16:45
end-sync_1 = 00:16:59
end = 2024-01-16 00:16:59.536766233+00:00

[server]
repo = "cake233/ubuntu-zsh-armv7"

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
ldd = 'ldd (Ubuntu GLIBC 2.38-3ubuntu1) 2.38'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabihf)'
```
