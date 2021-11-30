# ubuntu-zsh-armv7

## How to run it?

```shell
docker run \
    -it \
    --name ubuntu-zsh-armv7 \
    cake233/ubuntu-zsh-armv7
```

## How to exec shell?

```shell
    docker exec -it ubuntu-zsh-armv7 zsh
```

## ubuntu-zsh-armv7.toml

```toml
[main]
name = "ubuntu"
tag = ["zsh", "2021-11-30", "devel"]
os = "ubuntu"
release = "dev"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "ubuntu-zsh_armhf_2021-11-30_13-41.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "1b19a5294ce00196b4b6643f670e20d873c52569c2bbd825c9c5910ef43f4512"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "567M"
tar_bytes = 594428416

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "106M"
zstd_bytes = 110560714

[compatibility]
compatible_mode = true

last_version = "latest01"

# The value is &str, not int
last_date = "20211128"
last_tag = "2021-11-28"
last_file = "ubuntu-zsh-armv7_2021-11-28_21-09-rootfs.tar.zst"

current_version = "latest02"
current_date = "20211130"
old_file = ""
# edition 2021
# DISTRO_NAME=ubuntu-dev_armhf
# ROOTFS_FILE=ubuntu-zsh_armhf_2021-11-30_13-41-rootfs.tar.zst
# BUILD_DATE=20211130
# BUILD_TAG=2021-11-30
# STATUS=completed
# VERSION=latest02
# END_TIME=13:41

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-11-30
begin = 2021-11-30 13:26:14.363610249+00:00
start-sync_0 = 13:37:36
start-zstd = 13:39:18
start-sync_1 = 13:41:00
end-sync_1 = 13:41:14
end = 2021-11-30 13:41:14.838765885+00:00

[server]
repo = "cake233/ubuntu-zsh-armv7"

[server.node1]
name = "cn"
current = false
last = true
in_sync = false
split = false

[server.node2]
name = "us"
current = false
last = true
in_sync = false
split = false

[server.node3]
name = "global"
current = false
last = true
in_sync = false
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"
```
