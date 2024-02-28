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
tag = ["zsh", "2024-02-28"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-zsh_armhf_2024-02-28_00-25.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "45365a3bd2ee316438851fd2e78b8e4a29dfdfd124f2d79de0a2d23956bbdf6d"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "934M"
tar_bytes = 978383360

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "231M"
zstd_bytes = 241700519

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231122"
previous_tag = "2023-11-22"
previous_file = "arch-zsh_armhf_2023-11-22_00-30-rootfs.tar.zst"
previous_sha256 = "e2c81d50afa13a40f2cc5a679c123426f815126fb63b1fc76939abd86b962805"

current_version = "latest01"
current_date = "20240228"
old_file = "arch-zsh_armhf_2023-11-15_00-29-rootfs.tar.zst"
old_sha256 = "a02c12fb1d19bddba71603a7b6529e04a477231bf30f256387a47bceff411176"
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch-zsh_armhf_2024-02-28_00-25-rootfs.tar.zst
# SHA256SUM=45365a3bd2ee316438851fd2e78b8e4a29dfdfd124f2d79de0a2d23956bbdf6d
# BUILD_DATE=20240228
# BUILD_TAG=2024-02-28
# STATUS=completed
# VERSION=latest01
# END_TIME=00:25

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-02-28
begin = 2024-02-28 00:03:16.205693633+00:00
start-sync_0 = 00:19:55
start-zstd = 00:21:41
start-sync_1 = 00:24:51
end-sync_1 = 00:25:14
end = 2024-02-28 00:25:14.717513732+00:00

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
