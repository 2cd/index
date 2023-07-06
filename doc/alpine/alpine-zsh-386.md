# alpine-zsh-386

## How to run it?

```sh
docker run \
    -it \
    --name alpine-zsh-386 \
    cake233/alpine-zsh-386
```

## How to exec shell?

```sh
docker exec -it alpine-zsh-386 zsh
```

## alpine-zsh-386.toml

```toml
[main]
name = "alpine"
tag = ["zsh", "2023-07-06"]
os = "alpine"
release = "edge"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_i386_2023-07-06_00-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c70aebfeede27ed1b1b1ac847963a0172867c005b6ea171134b1d24b7b840170"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "92M"
tar_bytes = 95532544

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "31M"
zstd_bytes = 32215405

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230629"
previous_tag = "2023-06-29"
previous_file = "alpine-zsh_i386_2023-06-29_00-05-rootfs.tar.zst"
previous_sha256 = "4ad13aa0cb028fe342adcd7765fb3f5f6690e065a671efc1fdf7387e515cdd76"

current_version = "latest01"
current_date = "20230706"
old_file = "alpine-zsh_i386_2023-06-22_00-05-rootfs.tar.zst"
old_sha256 = "021f6e0a5602472c45c6438bd5996c13d4ff2b9bf7c5d927890e56195b6c0cd2"
# edition 2021
# DISTRO_NAME=alpine-edge_i386
# ROOTFS_FILE=alpine-zsh_i386_2023-07-06_00-06-rootfs.tar.zst
# SHA256SUM=c70aebfeede27ed1b1b1ac847963a0172867c005b6ea171134b1d24b7b840170
# BUILD_DATE=20230706
# BUILD_TAG=2023-07-06
# STATUS=completed
# VERSION=latest01
# END_TIME=00:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-06
begin = 2023-07-06 00:02:35.037344280+00:00
start-sync_0 = 00:04:25
start-zstd = 00:05:48
start-sync_1 = 00:06:23
end-sync_1 = 00:06:32
end = 2023-07-06 00:06:32.975436573+00:00

[server]
repo = "cake233/alpine-zsh-386"

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
LANG = "C.UTF-8"

[version]
ldd = 'musl libc (i386) Version 1.2.4'
zsh = 'zsh 5.9 (i586-alpine-linux-musl)'
```
