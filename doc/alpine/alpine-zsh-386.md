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
tag = ["zsh", "2022-10-13"]
os = "alpine"
release = "edge"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_i386_2022-10-13_00-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "851053cdf09d04a249d53885186d31111c86c3cb1e4ab331ce28ffd51af21877"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "92M"
tar_bytes = 96204800

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "30M"
zstd_bytes = 30825664

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221006"
previous_tag = "2022-10-06"
previous_file = "alpine-zsh_i386_2022-10-06_00-05-rootfs.tar.zst"
previous_sha256 = "8145e728d244cd5264f9021bc107565cc97c3a0a78752bb32e1024c26bed6c4c"

current_version = "latest02"
current_date = "20221013"
old_file = "alpine-zsh_i386_2022-09-29_00-05-rootfs.tar.zst"
old_sha256 = "214a1d6f44207fb62945938fcf10bf673cd5d5732aab651f818903d6379d98ac"
# edition 2021
# DISTRO_NAME=alpine-edge_i386
# ROOTFS_FILE=alpine-zsh_i386_2022-10-13_00-06-rootfs.tar.zst
# SHA256SUM=851053cdf09d04a249d53885186d31111c86c3cb1e4ab331ce28ffd51af21877
# BUILD_DATE=20221013
# BUILD_TAG=2022-10-13
# STATUS=completed
# VERSION=latest02
# END_TIME=00:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-13
begin = 2022-10-13 00:02:23.167757470+00:00
start-sync_0 = 00:04:13
start-zstd = 00:05:38
start-sync_1 = 00:06:09
end-sync_1 = 00:06:21
end = 2022-10-13 00:06:21.316353709+00:00

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
ldd = 'musl libc (i386) Version 1.2.3'
zsh = 'zsh 5.9 (i586-alpine-linux-musl)'
```
