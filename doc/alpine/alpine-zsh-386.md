# alpine-zsh-386

## How to run it?

```shell
docker run \
    -it \
    --name alpine-zsh-386 \
    cake233/alpine-zsh-386
```

## How to exec shell?

```shell
    docker exec -it alpine-zsh-386 zsh
```

## alpine-zsh-386.toml

```toml
[main]
name = "alpine"
tag = ["zsh", "2021-12-09"]
os = "alpine"
release = "edge"
arch = "i386"
platform = "linux/386"
x11_or_wayland = false

[file]
name = "alpine-zsh_i386_2021-12-09_00-05.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "cf741eb1de339a464bee94f3c00900e3dada76ba0f2fe7d15031891992f68f7b"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "93M"
tar_bytes = 97140224

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "27M"
zstd_bytes = 28293939

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211202"
previous_tag = "2021-12-02"
previous_file = "alpine-zsh_i386_2021-12-02_00-05-rootfs.tar.zst"
previous_sha256 = ""

current_version = "latest02"
current_date = "20211209"
old_file = "alpine-zsh_i386_2021-11-30_14-59-rootfs.tar.zst"
old_sha256 = ""
# edition 2021
# DISTRO_NAME=alpine-edge_i386
# ROOTFS_FILE=alpine-zsh_i386_2021-12-09_00-05-rootfs.tar.zst
# SHA256SUM=cf741eb1de339a464bee94f3c00900e3dada76ba0f2fe7d15031891992f68f7b
# BUILD_DATE=20211209
# BUILD_TAG=2021-12-09
# STATUS=completed
# VERSION=latest02
# END_TIME=00:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-09
begin = 2021-12-09 00:02:23.317710912+00:00
start-sync_0 = 00:03:43
start-zstd = 00:05:04
start-sync_1 = 00:05:37
end-sync_1 = 00:05:50
end = 2021-12-09 00:05:50.687702674+00:00

[server]
repo = "cake233/alpine-zsh-386"

[server.node1]
name = "cn"
current = false
previous = true
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
previous = true
in_sync = false
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "C.UTF-8"
```
