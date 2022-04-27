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
tag = ["zsh", "2022-04-27"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-zsh_arm64_2022-04-27_00-26.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ff6975a13c1f14685225f8c708ba3d40d329e03b0cbfef396324dee60a8d4d5f"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "960M"
tar_bytes = 1005601280

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "226M"
zstd_bytes = 236397123

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220420"
previous_tag = "2022-04-20"
previous_file = "arch-zsh_arm64_2022-04-20_00-22-rootfs.tar.zst"
previous_sha256 = "c2f3fcf49ed4ad29e58a349c90fa478e860a3d38df70bddf42c32b64dbfa853f"

current_version = "latest01"
current_date = "20220427"
old_file = "arch-zsh_arm64_2022-04-13_00-34-rootfs.tar.zst"
old_sha256 = "3ba5ed5dff9aea4c623d5829b4175924187a37904c57f5bc41ea3f73f00580c4"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-zsh_arm64_2022-04-27_00-26-rootfs.tar.zst
# SHA256SUM=ff6975a13c1f14685225f8c708ba3d40d329e03b0cbfef396324dee60a8d4d5f
# BUILD_DATE=20220427
# BUILD_TAG=2022-04-27
# STATUS=completed
# VERSION=latest01
# END_TIME=00:26

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-27
begin = 2022-04-27 00:08:24.300984927+00:00
start-sync_0 = 00:21:26
start-zstd = 00:23:13
start-sync_1 = 00:26:37
end-sync_1 = 00:26:58
end = 2022-04-27 00:26:58.489335732+00:00

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
zsh = 'zsh 5.8.1 (aarch64-unknown-linux-gnu)'
```
