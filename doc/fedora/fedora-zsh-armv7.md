# fedora-zsh-armv7

## How to run it?

```shell
docker run \
    -it \
    --name fedora-zsh-armv7 \
    cake233/fedora-zsh-armv7
```

## How to exec shell?

```shell
    docker exec -it fedora-zsh-armv7 zsh
```

## fedora-zsh-armv7.toml

```toml
[main]
name = "fedora"
tag = ["zsh", "2021-11-30"]
os = "fedora"
release = "rawhide"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "fedora-zsh_armhf_2021-11-30_12-18.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "834446d6e6750115a097e85ee08ecd6994181be5648be5c4e01fccdfdc9e79a3"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1107755008

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "198M"
zstd_bytes = 207218033

[compatibility]
compatible_mode = true

last_version = "latest01"

# The value is &str, not int
last_date = "20211128"
last_tag = "2021-11-28"
last_file = "fedora-zsh-armv7_2021-11-28_21-09-rootfs.tar.zst"

current_version = "latest02"
current_date = "20211130"
old_file = "fedora-rawhide_armhf+zsh-2021_11-02-rootfs.tar.zst"
# edition 2021
# DISTRO_NAME=fedora-rawhide_armhf
# ROOTFS_FILE=fedora-zsh_armhf_2021-11-30_12-18-rootfs.tar.zst
# BUILD_DATE=20211130
# BUILD_TAG=2021-11-30
# STATUS=completed
# VERSION=latest02
# END_TIME=12:18

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-11-30
begin = 2021-11-30 12:01:51.116594146+00:00
start-sync_0 = 12:12:19
start-zstd = 12:14:15
start-sync_1 = 12:17:54
end-sync_1 = 12:18:13
end = 2021-11-30 12:18:13.395662245+00:00

[server]
repo = "cake233/fedora-zsh-armv7"

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
