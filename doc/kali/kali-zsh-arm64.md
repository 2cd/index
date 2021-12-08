# kali-zsh-arm64

## How to run it?

```shell
docker run \
    -it \
    --name kali-zsh-arm64 \
    cake233/kali-zsh-arm64
```

## How to exec shell?

```shell
    docker exec -it kali-zsh-arm64 zsh
```

## kali-zsh-arm64.toml

```toml
[main]
name = "kali"
tag = ["zsh", "2021-12-02"]
os = "kali"
release = "rolling"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "kali-zsh_arm64_2021-12-02_12-18.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "4f4c7d9e021c535387cc23d5b76e55d1678ac2fcf439d244c7c47f7c40929a0e"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "723M"
tar_bytes = 757164032

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "140M"
zstd_bytes = 146262343

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211202"
previous_tag = "2021-12-02"
previous_file = "kali-zsh_arm64_2021-12-02_07-37-rootfs.tar.zst"

current_version = "latest02"
current_date = "20211202"
old_file = "kali-zsh_arm64_2021-11-30_15-15-rootfs.tar.zst"
# edition 2021
# DISTRO_NAME=kali-rolling_arm64
# ROOTFS_FILE=kali-zsh_arm64_2021-12-02_12-18-rootfs.tar.zst
# BUILD_DATE=20211202
# BUILD_TAG=2021-12-02
# STATUS=completed
# VERSION=latest02
# END_TIME=12:18

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-02
begin = 2021-12-02 12:01:51.043231684+00:00
start-sync_0 = 12:13:37
start-zstd = 12:15:23
start-sync_1 = 12:17:44
end-sync_1 = 12:18:00
end = 2021-12-02 12:18:00.531326935+00:00

[server]
repo = "cake233/kali-zsh-arm64"

[server.node1]
name = "cn"
current = false
previous = true
in_sync = false
split = false

[server.node2]
name = "us"
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "global"
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
```
