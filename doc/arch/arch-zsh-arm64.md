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
tag = ["zsh", "2022-08-03"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-zsh_arm64_2022-08-03_00-39.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "3ef7f317e65ec78fc83c00ed1dca479ece41a4fc8d6769596062eae1cbef2fac"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "957M"
tar_bytes = 1003279360

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "226M"
zstd_bytes = 236373893

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220713"
previous_tag = "2022-07-13"
previous_file = "arch-zsh_arm64_2022-07-13_00-37-rootfs.tar.zst"
previous_sha256 = "aae1d184449dfa97d269ea3da092721b68577b1912658ce60930e84c49721da5"

current_version = "latest01"
current_date = "20220803"
old_file = "arch-zsh_arm64_2022-07-06_00-27-rootfs.tar.zst"
old_sha256 = "91a097940aa10f555a3e65d02b24f0e983979d03b14e5c408d8e8b188fb509bc"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-zsh_arm64_2022-08-03_00-39-rootfs.tar.zst
# SHA256SUM=3ef7f317e65ec78fc83c00ed1dca479ece41a4fc8d6769596062eae1cbef2fac
# BUILD_DATE=20220803
# BUILD_TAG=2022-08-03
# STATUS=completed
# VERSION=latest01
# END_TIME=00:39

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-03
begin = 2022-08-03 00:12:14.720070169+00:00
start-sync_0 = 00:33:07
start-zstd = 00:34:41
start-sync_1 = 00:38:45
end-sync_1 = 00:39:08
end = 2022-08-03 00:39:08.100175905+00:00

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
