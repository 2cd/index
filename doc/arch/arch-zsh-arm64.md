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
tag = ["zsh", "2022-10-12"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-zsh_arm64_2022-10-12_00-26.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b451275656190c99ecfe0923986123cb321f12f15861bdd036f8d856d095b477"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "976M"
tar_bytes = 1022918144

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "230M"
zstd_bytes = 240941961

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221005"
previous_tag = "2022-10-05"
previous_file = "arch-zsh_arm64_2022-10-05_00-27-rootfs.tar.zst"
previous_sha256 = "e460ac85a5d722c61859ca2ce2a9ad9d06e013a17337d2900e4a554f7c24a9a6"

current_version = "latest02"
current_date = "20221012"
old_file = "arch-zsh_arm64_2022-09-28_00-35-rootfs.tar.zst"
old_sha256 = "5bebf4608534ecfb614ee0564487a3d63ae5df9606643316db286e00bd72be1f"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-zsh_arm64_2022-10-12_00-26-rootfs.tar.zst
# SHA256SUM=b451275656190c99ecfe0923986123cb321f12f15861bdd036f8d856d095b477
# BUILD_DATE=20221012
# BUILD_TAG=2022-10-12
# STATUS=completed
# VERSION=latest02
# END_TIME=00:26

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-12
begin = 2022-10-12 00:07:30.182975342+00:00
start-sync_0 = 00:20:35
start-zstd = 00:22:06
start-sync_1 = 00:25:47
end-sync_1 = 00:26:08
end = 2022-10-12 00:26:08.648937733+00:00

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
