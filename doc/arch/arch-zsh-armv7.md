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
tag = ["zsh", "2023-06-21"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-zsh_armhf_2023-06-21_00-32.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "812f893f451c3327e66bb79aa1d50131f6a0f15a17d6ed2f547eb3954d38861b"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "924M"
tar_bytes = 968459776

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "225M"
zstd_bytes = 235855041

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230614"
previous_tag = "2023-06-14"
previous_file = "arch-zsh_armhf_2023-06-14_00-37-rootfs.tar.zst"
previous_sha256 = "9007937c53d91f3ce3fc531efe2e50d7e511ac1391eb7fd6d2688055e1c9c504"

current_version = "latest02"
current_date = "20230621"
old_file = "arch-zsh_armhf_2023-06-07_00-31-rootfs.tar.zst"
old_sha256 = "2ae9b2d0d70332fd5fabb37c9aebc894b5e38ec34f095e84da075357ac556acb"
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch-zsh_armhf_2023-06-21_00-32-rootfs.tar.zst
# SHA256SUM=812f893f451c3327e66bb79aa1d50131f6a0f15a17d6ed2f547eb3954d38861b
# BUILD_DATE=20230621
# BUILD_TAG=2023-06-21
# STATUS=completed
# VERSION=latest02
# END_TIME=00:32

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-21
begin = 2023-06-21 00:09:08.769108909+00:00
start-sync_0 = 00:26:33
start-zstd = 00:28:04
start-sync_1 = 00:32:23
end-sync_1 = 00:32:44
end = 2023-06-21 00:32:44.561444503+00:00

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
