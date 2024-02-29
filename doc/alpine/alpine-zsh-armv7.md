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
tag = ["zsh", "2024-02-29"]
os = "alpine"
release = "edge"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_armhf_2024-02-29_00-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "38291e753f0e6b71878b9741de6043f895f3b992d7d6ce2b30a4eb2e7b183e8b"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "106M"
tar_bytes = 110900736

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "39M"
zstd_bytes = 39891846

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231123"
previous_tag = "2023-11-23"
previous_file = "alpine-zsh_armhf_2023-11-23_00-06-rootfs.tar.zst"
previous_sha256 = "838676abc11a79da6aa1c48957255c253e5eddba16932ac8379eb51daf91c4b9"

current_version = "latest02"
current_date = "20240229"
old_file = "alpine-zsh_armhf_2023-11-16_00-06-rootfs.tar.zst"
old_sha256 = "d2038a5ac1c02a9ac1eb7b67fa1085f122452643ee3e73813af9f523d1880e60"
# edition 2021
# DISTRO_NAME=alpine-edge_armhf
# ROOTFS_FILE=alpine-zsh_armhf_2024-02-29_00-06-rootfs.tar.zst
# SHA256SUM=38291e753f0e6b71878b9741de6043f895f3b992d7d6ce2b30a4eb2e7b183e8b
# BUILD_DATE=20240229
# BUILD_TAG=2024-02-29
# STATUS=completed
# VERSION=latest02
# END_TIME=00:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-02-29
begin = 2024-02-29 00:02:32.516961347+00:00
start-sync_0 = 00:04:00
start-zstd = 00:05:25
start-sync_1 = 00:05:55
end-sync_1 = 00:06:05
end = 2024-02-29 00:06:05.690310553+00:00

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
ldd = 'musl libc (armhf) Version 1.2.4_git20230717'
zsh = 'zsh 5.9 (armv7-alpine-linux-musleabihf)'
```
