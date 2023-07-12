# arch-zsh-amd64

## How to run it?

```sh
docker run \
    -it \
    --name arch-zsh-amd64 \
    cake233/arch-zsh-amd64
```

## How to exec shell?

```sh
docker exec -it arch-zsh-amd64 zsh
```

## arch-zsh-amd64.toml

```toml
[main]
name = "arch"
tag = ["zsh", "2023-07-12"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-zsh_amd64_2023-07-12_00-16.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "bca54eb2fac8674d0b0c808b485672cfdeea4ebcc49f54bc5bc3dca57f5437d4"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1162350592

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "278M"
zstd_bytes = 291377390

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230705"
previous_tag = "2023-07-05"
previous_file = "arch-zsh_amd64_2023-07-05_00-16-rootfs.tar.zst"
previous_sha256 = "b1201d3d59ba9449dcfe9c0ebbb187e46ab0dacc45aaeabb145d2b2006911cf9"

current_version = "latest02"
current_date = "20230712"
old_file = "arch-zsh_amd64_2023-06-28_00-19-rootfs.tar.zst"
old_sha256 = "8e98ca833cb56b13a7bfc6590aa067d2c74b364b57623bbf68efd9b3f17bb779"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-zsh_amd64_2023-07-12_00-16-rootfs.tar.zst
# SHA256SUM=bca54eb2fac8674d0b0c808b485672cfdeea4ebcc49f54bc5bc3dca57f5437d4
# BUILD_DATE=20230712
# BUILD_TAG=2023-07-12
# STATUS=completed
# VERSION=latest02
# END_TIME=00:16

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-12
begin = 2023-07-12 00:07:45.243604134+00:00
start-sync_0 = 00:10:34
start-zstd = 00:12:03
start-sync_1 = 00:16:19
end-sync_1 = 00:16:40
end = 2023-07-12 00:16:40.358682289+00:00

[server]
repo = "cake233/arch-zsh-amd64"

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
ldd = 'ldd (GNU libc) 2.37'
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'
```
