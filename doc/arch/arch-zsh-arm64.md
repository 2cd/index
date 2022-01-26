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
tag = ["zsh", "2022-01-26"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "arch-zsh_arm64_2022-01-26_00-28.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "8992209cbe0d111647c71b80f31d0c4cb768a06f61dd3bd4a33d69c91b96c719"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "963M"
tar_bytes = 1009370112

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "221M"
zstd_bytes = 230916101

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220119"
previous_tag = "2022-01-19"
previous_file = "arch-zsh_arm64_2022-01-19_00-29-rootfs.tar.zst"
previous_sha256 = "70dd5c304ebae67d5d4ee439deeb42e4f6faf797492ebe54a836b376a89776b8"

current_version = "latest02"
current_date = "20220126"
old_file = "arch-zsh_arm64_2022-01-05_00-19-rootfs.tar.zst"
old_sha256 = "4a143dfe94ad9c662b4cc56639efbdcdfdb8629f30fbab88a4f71915d6621161"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-zsh_arm64_2022-01-26_00-28-rootfs.tar.zst
# SHA256SUM=8992209cbe0d111647c71b80f31d0c4cb768a06f61dd3bd4a33d69c91b96c719
# BUILD_DATE=20220126
# BUILD_TAG=2022-01-26
# STATUS=completed
# VERSION=latest02
# END_TIME=00:28

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-26
begin = 2022-01-26 00:08:10.864845520+00:00
start-sync_0 = 00:22:37
start-zstd = 00:24:25
start-sync_1 = 00:28:20
end-sync_1 = 00:28:45
end = 2022-01-26 00:28:45.619418912+00:00

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
ldd = 'ldd (GNU libc) 2.32'
zsh = 'zsh 5.8 (aarch64-unknown-linux-gnu)'
```
