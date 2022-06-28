# fedora-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name fedora-zsh-arm64 \
    cake233/fedora-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it fedora-zsh-arm64 zsh
```

## fedora-zsh-arm64.toml

```toml
[main]
name = "fedora"
tag = ["zsh", "2022-06-28"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-zsh_arm64_2022-06-28_12-40.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "fc1d08813f00128113ff99076ee772bb1bc1e682f0cb54bf980355ae01d73376"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1122025472

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "175M"
zstd_bytes = 183121860

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220621"
previous_tag = "2022-06-21"
previous_file = "fedora-zsh_arm64_2022-06-21_12-54-rootfs.tar.zst"
previous_sha256 = "913049f8f99de6b62ac81c0b6ff634fa0a07ea2b00065d2a0d9d227cd91c9240"

current_version = "latest02"
current_date = "20220628"
old_file = "fedora-zsh_arm64_2022-06-14_12-47-rootfs.tar.zst"
old_sha256 = "9f95a69654949bdc0e5af39096b2f5f3a284d090ff0104b1f2fad643f8bb57d6"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-zsh_arm64_2022-06-28_12-40-rootfs.tar.zst
# SHA256SUM=fc1d08813f00128113ff99076ee772bb1bc1e682f0cb54bf980355ae01d73376
# BUILD_DATE=20220628
# BUILD_TAG=2022-06-28
# STATUS=completed
# VERSION=latest02
# END_TIME=12:40

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-28
begin = 2022-06-28 12:02:30.262402009+00:00
start-sync_0 = 12:35:10
start-zstd = 12:37:07
start-sync_1 = 12:40:14
end-sync_1 = 12:40:30
end = 2022-06-28 12:40:30.473914236+00:00

[server]
repo = "cake233/fedora-zsh-arm64"

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
ldd = 'ldd (GNU libc) 2.35.9000'
zsh = 'zsh 5.9 (aarch64-redhat-linux-gnu)'
```
