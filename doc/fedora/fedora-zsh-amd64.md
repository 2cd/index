# fedora-zsh-amd64

## How to run it?

```shell
docker run \
    -it \
    --name fedora-zsh-amd64 \
    cake233/fedora-zsh-amd64
```

## How to exec shell?

```shell
    docker exec -it fedora-zsh-amd64 zsh
```

## fedora-zsh-amd64.toml

```toml
[main]
name = "fedora"
tag = ["zsh", "2021-11-28"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "fedora-zsh-amd64_2021-11-28_21-00.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "c9648dd0f60a09661d0b6a30658f3b16a90f6dcacd4004131df4c3bdf0bd960d"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.2G"
tar_bytes = 1203495424

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "215M"
zstd_bytes = 224458265

[compatibility]
compatible_mode = true

last_version = "latest02"

# The value is &str, not int
last_date = "20211102"
last_tag = ""
last_file = "fedora-rawhide_amd64+zsh-2021_11-02-rootfs.tar.zst"

current_version = "latest01"
current_date = "20211128"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-zsh-amd64_2021-11-28_21-00-rootfs.tar.zst
# BUILD_DATE=20211128
# BUILD_TAG=2021-11-28
# STATUS=completed
# VERSION=latest01
# END_TIME=21:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-11-28
begin = 2021-11-28 20:51:10.304069480+00:00
start-sync_0 = 20:54:10
start-zstd = 20:56:09
start-sync_1 = 20:59:54
end-sync_1 = 21:00:14
end = 2021-11-28 21:00:14.168277114+00:00

[server]
repo = "cake233/fedora-zsh-amd64"

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
