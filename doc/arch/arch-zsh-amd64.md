# arch-zsh-amd64

## How to run it?

```sh
docker run \
    -it \
    --name arch-zsh-amd64 \
    cake233/arch-zsh-amd64
```

## How to exec shell?

```sh
docker exec -it arch-zsh-amd64 zsh
```

## arch-zsh-amd64.toml

```toml
[main]
name = "arch"
tag = ["zsh", "2022-11-30"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-zsh_amd64_2022-11-30_00-17.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "60c2a55fb1c93858ecd104dbebdd081522f91fddd1e7134808baa3d181551e1f"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1095554048

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "263M"
zstd_bytes = 275155246

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221123"
previous_tag = "2022-11-23"
previous_file = "arch-zsh_amd64_2022-11-23_00-17-rootfs.tar.zst"
previous_sha256 = "f5c5eb1c2e7f3f584d10890950ec368c702c88716ceb53192e428542020f5d06"

current_version = "latest01"
current_date = "20221130"
old_file = "arch-zsh_amd64_2022-11-20_20-28-rootfs.tar.zst"
old_sha256 = "53cb8c5b149f80c8d1726139a30cdbd45ed954df2d75a8e9b29ead283b47b263"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-zsh_amd64_2022-11-30_00-17-rootfs.tar.zst
# SHA256SUM=60c2a55fb1c93858ecd104dbebdd081522f91fddd1e7134808baa3d181551e1f
# BUILD_DATE=20221130
# BUILD_TAG=2022-11-30
# STATUS=completed
# VERSION=latest01
# END_TIME=00:17

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-30
begin = 2022-11-30 00:07:46.139366908+00:00
start-sync_0 = 00:11:18
start-zstd = 00:12:50
start-sync_1 = 00:16:40
end-sync_1 = 00:17:02
end = 2022-11-30 00:17:02.170443965+00:00

[server]
repo = "cake233/arch-zsh-amd64"

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
ldd = 'ldd (GNU libc) 2.36'
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'
```
