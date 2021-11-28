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
name = "fedora-zsh-arm64_2021-11-28_14-26.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "efa763dd1af9ee8b448923ea57b572cc6fbb8e4fe32b36c3f5783b183cb349a6"

# zstd: [1-22]
zstd-level = 13

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.2G"
tar_bytes = 1240489472

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "286M"
zstd_bytes = 299836877

[compatibility]
compatible_mode = true
current_version = "latest01"
current_date = 20211128
last_version = "latest02"
last_date = 20211102
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-zsh-arm64_2021-11-28_14-26.tar.zst
# BUILD_DATE=20211128
# STATUS=completed
# VERSION=latest01
# END_TIME=14:26

[time]
format = "rfc-3339"
zone = "UTC"
begin = 2021-11-28 13:52:19.439706907+00:00
start-sync_0 = 14:23:08
start-zstd = 14:25:09
start-sync_1 = 14:25:58
end-sync_1 = 14:26:24
end = 2021-11-28 14:26:24.300312279+00:00

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
last = false
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"
```
