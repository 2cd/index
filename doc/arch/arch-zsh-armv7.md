# arch-zsh-armv7

## How to run it?

```sh
docker run \
    -it \
    --name arch-zsh-armv7 \
    cake233/arch-zsh-armv7
```

## How to exec shell?

```sh
docker exec -it arch-zsh-armv7 zsh
```

## arch-zsh-armv7.toml

```toml
[main]
name = "arch"
tag = ["zsh", "2023-05-31"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-zsh_armhf_2023-05-31_00-30.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8456071d0dada0091a3442952ac55d9094a1fab71881ca4592a5dd2b86a95a87"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "914M"
tar_bytes = 957894656

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "224M"
zstd_bytes = 234288470

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230524"
previous_tag = "2023-05-24"
previous_file = "arch-zsh_armhf_2023-05-24_00-35-rootfs.tar.zst"
previous_sha256 = "d4551424876dd113a00c7b09c40239219bfbbca1bc4954f3a69f8c3f33ec440f"

current_version = "latest01"
current_date = "20230531"
old_file = "arch-zsh_armhf_2023-05-17_00-35-rootfs.tar.zst"
old_sha256 = "045449f52d08aea0d87105c60bf7d782bb2f59585884f76bdb7ac2a44fa98300"
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch-zsh_armhf_2023-05-31_00-30-rootfs.tar.zst
# SHA256SUM=8456071d0dada0091a3442952ac55d9094a1fab71881ca4592a5dd2b86a95a87
# BUILD_DATE=20230531
# BUILD_TAG=2023-05-31
# STATUS=completed
# VERSION=latest01
# END_TIME=00:30

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-05-31
begin = 2023-05-31 00:07:38.112458345+00:00
start-sync_0 = 00:25:14
start-zstd = 00:26:42
start-sync_1 = 00:30:24
end-sync_1 = 00:30:42
end = 2023-05-31 00:30:42.769653053+00:00

[server]
repo = "cake233/arch-zsh-armv7"

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
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.9 (armv7l-unknown-linux-gnueabihf)'
```
