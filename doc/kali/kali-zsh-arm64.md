# kali-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name kali-zsh-arm64 \
    cake233/kali-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it kali-zsh-arm64 zsh
```

## kali-zsh-arm64.toml

```toml
[main]
name = "kali"
tag = ["zsh", "2023-04-27"]
os = "kali"
release = "rolling"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_arm64_2023-04-27_12-18.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "22debf324826392b997b055c5404fbd69450a7a855287011c7c549d508ec14c1"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "816M"
tar_bytes = 854892032

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "149M"
zstd_bytes = 156129395

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230413"
previous_tag = "2023-04-13"
previous_file = "kali-zsh_arm64_2023-04-13_12-18-rootfs.tar.zst"
previous_sha256 = "7912654caf95a178e08a64139cb8494358ff60f12c4dee85b234084e53d68782"

current_version = "latest02"
current_date = "20230427"
old_file = "kali-zsh_arm64_2023-04-06_12-18-rootfs.tar.zst"
old_sha256 = "b0bd4c767bd975f91a6608cbb6b2da50aa52a5550e199363809d21173d2f9ab3"
# edition 2021
# DISTRO_NAME=kali-rolling_arm64
# ROOTFS_FILE=kali-zsh_arm64_2023-04-27_12-18-rootfs.tar.zst
# SHA256SUM=22debf324826392b997b055c5404fbd69450a7a855287011c7c549d508ec14c1
# BUILD_DATE=20230427
# BUILD_TAG=2023-04-27
# STATUS=completed
# VERSION=latest02
# END_TIME=12:18

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-27
begin = 2023-04-27 12:02:32.979020579+00:00
start-sync_0 = 12:13:59
start-zstd = 12:15:43
start-sync_1 = 12:18:09
end-sync_1 = 12:18:22
end = 2023-04-27 12:18:22.030988333+00:00

[server]
repo = "cake233/kali-zsh-arm64"

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
ldd = 'ldd (Debian GLIBC 2.36-9) 2.36'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'
```
