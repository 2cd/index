# debian-zsh-386

## How to run it?

```shell
docker run \
    -it \
    --name debian-zsh-386 \
    cake233/debian-zsh-386
```

## How to exec shell?

```shell
    docker exec -it debian-zsh-386 zsh
```

## debian-zsh-386.toml

```toml
[main]
name = "debian"
tag = ["zsh", "2021-11-28"]
os = "debian"
release = "sid"
arch = "i386"
platform = "linux/386"
x11_or_wayland = false

[file]
name = "debian-zsh-386_2021-11-28_21-10.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "b04b35d33bb7814f2d8784e83f2ac5d1bc634ee32d43940d2bbb68a7fa9bc61b"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "727M"
tar_bytes = 761786368

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "142M"
zstd_bytes = 148333554

[compatibility]
compatible_mode = true

last_version = "latest02"

# The value is &str, not int
last_date = "20211103"
last_tag = ""
last_file = "debian-sid_i386+zsh-2021_11-03-rootfs.tar.zst"

current_version = "latest01"
current_date = "20211128"
# edition 2021
# DISTRO_NAME=debian-sid_i386
# ROOTFS_FILE=debian-zsh-386_2021-11-28_21-10-rootfs.tar.zst
# BUILD_DATE=20211128
# BUILD_TAG=2021-11-28
# STATUS=completed
# VERSION=latest01
# END_TIME=21:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-11-28
begin = 2021-11-28 20:51:10.763199581+00:00
start-sync_0 = 21:05:48
start-zstd = 21:07:38
start-sync_1 = 21:09:58
end-sync_1 = 21:10:14
end = 2021-11-28 21:10:14.225570140+00:00

[server]
repo = "cake233/debian-zsh-386"

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
