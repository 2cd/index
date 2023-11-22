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
tag = ["zsh", "2023-11-22"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-zsh_arm64_2023-11-22_00-28.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "494d04accb42a0e42218ff1ff555e261b6e1031f5eb0e6f0b5be21ad900262a2"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1084879360

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "243M"
zstd_bytes = 253970228

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231115"
previous_tag = "2023-11-15"
previous_file = "arch-zsh_arm64_2023-11-15_00-31-rootfs.tar.zst"
previous_sha256 = "6a2b53196bbedc2899f5214c736d39db2b145bb51ce1a7dcf82f4a498ead0534"

current_version = "latest02"
current_date = "20231122"
old_file = "arch-zsh_arm64_2023-11-08_00-28-rootfs.tar.zst"
old_sha256 = "b6d365978d6d58fed06c50312400d873d7294226c6cd3c6b2a559043aa523158"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-zsh_arm64_2023-11-22_00-28-rootfs.tar.zst
# SHA256SUM=494d04accb42a0e42218ff1ff555e261b6e1031f5eb0e6f0b5be21ad900262a2
# BUILD_DATE=20231122
# BUILD_TAG=2023-11-22
# STATUS=completed
# VERSION=latest02
# END_TIME=00:28

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-11-22
begin = 2023-11-22 00:09:27.798456384+00:00
start-sync_0 = 00:23:09
start-zstd = 00:24:37
start-sync_1 = 00:27:53
end-sync_1 = 00:28:11
end = 2023-11-22 00:28:11.815484744+00:00

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
