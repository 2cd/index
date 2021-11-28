# arch-zsh-armv7

## How to run it?

```shell
docker run \
    -it \
    --name arch-zsh-armv7 \
    cake233/arch-zsh-armv7
```

## How to exec shell?

```shell
    docker exec -it arch-zsh-armv7 zsh
```

## arch-zsh-armv7.toml

```toml
[main]
name = "arch"
tag = ["zsh", "2021-11-28"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "arch-zsh-armv7_2021-11-28_19-01.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "bb1092d82a71413b2bd425581bfcd3a740139c2329872e9001f729b4ec3962c1"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "847M"
tar_bytes = 887712256

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "206M"
zstd_bytes = 215945758

[compatibility]
compatible_mode = true

last_version = "latest02"

# The value is &str, not int
last_date = "20211103"
last_tag = ""
last_file = "arch_armhf+zsh-2021_11-03-rootfs.tar.zst"

current_version = "latest01"
current_date = "20211128"
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch-zsh-armv7_2021-11-28_19-01.tar.zst
# BUILD_DATE=20211128
# BUILD_TAG=2021-11-28
# STATUS=completed
# VERSION=latest01
# END_TIME=19:01

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-11-28
begin = 2021-11-28 18:42:22.620614056+00:00
start-sync_0 = 18:56:04
start-zstd = 18:57:45
start-sync_1 = 19:01:34
end-sync_1 = 19:01:54
end = 2021-11-28 19:01:54.606058689+00:00

[server]
repo = "cake233/arch-zsh-armv7"

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
