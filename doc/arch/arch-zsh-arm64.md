# arch-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name arch-zsh-arm64 \
    cake233/arch-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it arch-zsh-arm64 zsh
```

## arch-zsh-arm64.toml

```toml
[main]
name = "arch"
tag = ["zsh", "2023-12-20"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-zsh_arm64_2023-12-20_00-28.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f5cbce9a0f4bfd9d5e6742768dbaf39d59ea1be24b1a92501669f7d05a652884"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1090581504

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "244M"
zstd_bytes = 255450590

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231122"
previous_tag = "2023-11-22"
previous_file = "arch-zsh_arm64_2023-11-22_00-28-rootfs.tar.zst"
previous_sha256 = "494d04accb42a0e42218ff1ff555e261b6e1031f5eb0e6f0b5be21ad900262a2"

current_version = "latest01"
current_date = "20231220"
old_file = "arch-zsh_arm64_2023-11-15_00-31-rootfs.tar.zst"
old_sha256 = "6a2b53196bbedc2899f5214c736d39db2b145bb51ce1a7dcf82f4a498ead0534"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-zsh_arm64_2023-12-20_00-28-rootfs.tar.zst
# SHA256SUM=f5cbce9a0f4bfd9d5e6742768dbaf39d59ea1be24b1a92501669f7d05a652884
# BUILD_DATE=20231220
# BUILD_TAG=2023-12-20
# STATUS=completed
# VERSION=latest01
# END_TIME=00:28

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-12-20
begin = 2023-12-20 00:09:48.231816195+00:00
start-sync_0 = 00:23:19
start-zstd = 00:24:47
start-sync_1 = 00:28:12
end-sync_1 = 00:28:30
end = 2023-12-20 00:28:30.589957939+00:00

[server]
repo = "cake233/arch-zsh-arm64"

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
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'
```
