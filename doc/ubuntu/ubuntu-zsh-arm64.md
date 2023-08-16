# ubuntu-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name ubuntu-zsh-arm64 \
    cake233/ubuntu-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it ubuntu-zsh-arm64 zsh
```

## ubuntu-zsh-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["zsh", "2023-08-16", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-zsh_arm64_2023-08-16_14-42.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b5ca7dff51a65e11fd2b5b99137616ea6383a7cc008aeb166c4af94ef812ec0d"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "762M"
tar_bytes = 798557696

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "140M"
zstd_bytes = 146182739

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221025"
previous_tag = "2022-10-25"
previous_file = "ubuntu-zsh_arm64_2022-10-25_00-21-rootfs.tar.zst"
previous_sha256 = "e5ca70546683d3d50ba1887dc83fe8a12798c71812b6c60a013ac19ba73bf514"

current_version = "latest02"
current_date = "20230816"
old_file = "ubuntu-zsh_arm64_2022-10-18_00-24-rootfs.tar.zst"
old_sha256 = "f561ce8330bc92d8cd600d4d7427dd704be6852dd5c5776ae597a96e5a667817"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-zsh_arm64_2023-08-16_14-42-rootfs.tar.zst
# SHA256SUM=b5ca7dff51a65e11fd2b5b99137616ea6383a7cc008aeb166c4af94ef812ec0d
# BUILD_DATE=20230816
# BUILD_TAG=2023-08-16
# STATUS=completed
# VERSION=latest02
# END_TIME=14:42

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-16
begin = 2023-08-16 14:21:20.358022277+00:00
start-sync_0 = 14:37:59
start-zstd = 14:39:51
start-sync_1 = 14:42:37
end-sync_1 = 14:42:55
end = 2023-08-16 14:42:55.597080620+00:00

[server]
repo = "cake233/ubuntu-zsh-arm64"

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
ldd = 'ldd (Ubuntu GLIBC 2.37-0ubuntu2) 2.37'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'
```
