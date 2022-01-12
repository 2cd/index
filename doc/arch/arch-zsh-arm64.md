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
tag = ["zsh", "2022-01-12"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "arch-zsh_arm64_2022-01-12_00-21.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "24f1a16736c568986ce69d5a9b3e0320f9bd0efcebf5906beda8141b3ae397ef"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "964M"
tar_bytes = 1010201088

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "221M"
zstd_bytes = 231322337

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220105"
previous_tag = "2022-01-05"
previous_file = "arch-zsh_arm64_2022-01-05_00-19-rootfs.tar.zst"
previous_sha256 = "4a143dfe94ad9c662b4cc56639efbdcdfdb8629f30fbab88a4f71915d6621161"

current_version = "latest01"
current_date = "20220112"
old_file = "arch-zsh_arm64_2021-12-29_00-17-rootfs.tar.zst"
old_sha256 = "6ab8db2383bca775bccab0808f10cf2e45ac18cf7b033f7269f3e850dfdf1777"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-zsh_arm64_2022-01-12_00-21-rootfs.tar.zst
# SHA256SUM=24f1a16736c568986ce69d5a9b3e0320f9bd0efcebf5906beda8141b3ae397ef
# BUILD_DATE=20220112
# BUILD_TAG=2022-01-12
# STATUS=completed
# VERSION=latest01
# END_TIME=00:21

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-12
begin = 2022-01-12 00:06:43.852936073+00:00
start-sync_0 = 00:15:05
start-zstd = 00:16:53
start-sync_1 = 00:20:53
end-sync_1 = 00:21:18
end = 2022-01-12 00:21:18.506728230+00:00

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
