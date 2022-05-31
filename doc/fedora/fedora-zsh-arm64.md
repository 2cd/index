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
tag = ["zsh", "2022-05-31"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-zsh_arm64_2022-05-31_12-46.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "42f4034ac2d32b39d2eacf7858e00c194fcaeabcada6a61d9cb0bbd7cf3f99b6"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "976M"
tar_bytes = 1022892032

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "156M"
zstd_bytes = 163386054

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220524"
previous_tag = "2022-05-24"
previous_file = "fedora-zsh_arm64_2022-05-24_12-41-rootfs.tar.zst"
previous_sha256 = "9d7d8f06605fd9df65a66a34e88428861df228cd58d169a42ef15ee846c93c2d"

current_version = "latest02"
current_date = "20220531"
old_file = "fedora-zsh_arm64_2022-05-17_12-43-rootfs.tar.zst"
old_sha256 = "45e83b120daca245336094d0f61fd2d38dc971a4646eb602d02e9cd05213de76"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-zsh_arm64_2022-05-31_12-46-rootfs.tar.zst
# SHA256SUM=42f4034ac2d32b39d2eacf7858e00c194fcaeabcada6a61d9cb0bbd7cf3f99b6
# BUILD_DATE=20220531
# BUILD_TAG=2022-05-31
# STATUS=completed
# VERSION=latest02
# END_TIME=12:46

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-31
begin = 2022-05-31 12:02:43.358968968+00:00
start-sync_0 = 12:41:18
start-zstd = 12:43:21
start-sync_1 = 12:46:38
end-sync_1 = 12:46:59
end = 2022-05-31 12:46:59.230651489+00:00

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
