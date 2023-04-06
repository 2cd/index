# alpine-zsh-armv7

## How to run it?

```sh
docker run \
    -it \
    --name alpine-zsh-armv7 \
    cake233/alpine-zsh-armv7
```

## How to exec shell?

```sh
docker exec -it alpine-zsh-armv7 zsh
```

## alpine-zsh-armv7.toml

```toml
[main]
name = "alpine"
tag = ["zsh", "2023-04-06"]
os = "alpine"
release = "edge"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_armhf_2023-04-06_00-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "cff07f77fa749fde96293bfb4229fb3908b7441c22cc9d643151162d651d4470"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "81M"
tar_bytes = 84124160

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "30M"
zstd_bytes = 30911565

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230330"
previous_tag = "2023-03-30"
previous_file = "alpine-zsh_armhf_2023-03-30_00-05-rootfs.tar.zst"
previous_sha256 = "163d5aaee635a14440b2966550f57c4d3b3d4ffbed42973e035ea43cdd4b946c"

current_version = "latest02"
current_date = "20230406"
old_file = "alpine-zsh_armhf_2023-03-23_00-05-rootfs.tar.zst"
old_sha256 = "612d5fe9a16ca8afceda57f4c6391b12245525646de93d17cc3a7146b28412af"
# edition 2021
# DISTRO_NAME=alpine-edge_armhf
# ROOTFS_FILE=alpine-zsh_armhf_2023-04-06_00-06-rootfs.tar.zst
# SHA256SUM=cff07f77fa749fde96293bfb4229fb3908b7441c22cc9d643151162d651d4470
# BUILD_DATE=20230406
# BUILD_TAG=2023-04-06
# STATUS=completed
# VERSION=latest02
# END_TIME=00:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-06
begin = 2023-04-06 00:02:26.631438131+00:00
start-sync_0 = 00:04:14
start-zstd = 00:05:39
start-sync_1 = 00:06:04
end-sync_1 = 00:06:15
end = 2023-04-06 00:06:15.510698579+00:00

[server]
repo = "cake233/alpine-zsh-armv7"

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
ldd = 'musl libc (armhf) Version 1.2.3'
zsh = 'zsh 5.9 (armv7-alpine-linux-musleabihf)'
```
