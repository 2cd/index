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
tag = ["zsh", "2022-12-29"]
os = "alpine"
release = "edge"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_armhf_2022-12-29_00-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "75c66b040d50b4265416234f700a1e4b28c393c548ae170295278ea2de142a5f"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "85M"
tar_bytes = 88835584

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "28M"
zstd_bytes = 28562038

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221222"
previous_tag = "2022-12-22"
previous_file = "alpine-zsh_armhf_2022-12-22_00-05-rootfs.tar.zst"
previous_sha256 = "f2d57dce50c49a0011a4158726319d64378a54ed04581750b44f3cdbb31add7b"

current_version = "latest01"
current_date = "20221229"
old_file = "alpine-zsh_armhf_2022-12-15_00-05-rootfs.tar.zst"
old_sha256 = "d2f3eb3077079232795bf6d5122ae4b1e23ccab614ccaacfc1e9c22508afee67"
# edition 2021
# DISTRO_NAME=alpine-edge_armhf
# ROOTFS_FILE=alpine-zsh_armhf_2022-12-29_00-06-rootfs.tar.zst
# SHA256SUM=75c66b040d50b4265416234f700a1e4b28c393c548ae170295278ea2de142a5f
# BUILD_DATE=20221229
# BUILD_TAG=2022-12-29
# STATUS=completed
# VERSION=latest01
# END_TIME=00:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-29
begin = 2022-12-29 00:02:29.567245902+00:00
start-sync_0 = 00:04:34
start-zstd = 00:05:57
start-sync_1 = 00:06:24
end-sync_1 = 00:06:33
end = 2022-12-29 00:06:33.621717796+00:00

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
