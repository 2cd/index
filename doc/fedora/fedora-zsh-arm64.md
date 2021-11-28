# fedora-zsh-arm64

## How to run it?

```shell
docker run \
    -it \
    --name fedora-zsh-arm64 \
    cake233/fedora-zsh-arm64
```

## How to exec shell?

```shell
    docker exec -it fedora-zsh-arm64 zsh
```

## fedora-zsh-arm64.toml

```toml
[main]
name = "fedora"
tag = ["zsh", "2021-11-28"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "fedora-zsh-arm64_2021-11-28_21-29.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "592dfae97b97358670095b0553ecd4530c1f9e60c8a72166b63cd915cd554621"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.2G"
tar_bytes = 1240491520

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "208M"
zstd_bytes = 217118413

[compatibility]
compatible_mode = true

last_version = "latest02"

# The value is &str, not int
last_date = "20211102"
last_tag = ""
last_file = "fedora-rawhide_arm64+zsh-2021_11-02-rootfs.tar.zst"

current_version = "latest01"
current_date = "20211128"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-zsh-arm64_2021-11-28_21-29.tar.zst
# BUILD_DATE=20211128
# BUILD_TAG=2021-11-28
# STATUS=completed
# VERSION=latest01
# END_TIME=21:29

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-11-28
begin = 2021-11-28 20:51:14.469411592+00:00
start-sync_0 = 21:23:19
start-zstd = 21:25:20
start-sync_1 = 21:29:02
end-sync_1 = 21:29:23
end = 2021-11-28 21:29:23.124945644+00:00

[server]
repo = "cake233/fedora-zsh-arm64"

[server.node1]
name = "cn"
current = false
last = true
split = false

[server.node2]
name = "us"
current = false
last = false
split = false
part = 12

[server.node3]
name = "global"
current = false
last = true
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"
```
