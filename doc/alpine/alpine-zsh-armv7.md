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
tag = ["zsh", "2022-07-21"]
os = "alpine"
release = "edge"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_armhf_2022-07-21_00-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5d794ab799cb983d9d19233782c71c7f5ed772415baafaa59e6be3cc0b734119"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "76M"
tar_bytes = 79400960

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "27M"
zstd_bytes = 27608857

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220714"
previous_tag = "2022-07-14"
previous_file = "alpine-zsh_armhf_2022-07-14_00-05-rootfs.tar.zst"
previous_sha256 = "399d9b80d9f63ecfdd4baa50a43ee53af49b7080ff46a0440478550baa0ee450"

current_version = "latest02"
current_date = "20220721"
old_file = "alpine-zsh_armhf_2022-07-07_00-05-rootfs.tar.zst"
old_sha256 = "94dcbf1f9e115211df1ea644fbaf98dbae3a11f09ec26b5ac91fe59dfdd2c77d"
# edition 2021
# DISTRO_NAME=alpine-edge_armhf
# ROOTFS_FILE=alpine-zsh_armhf_2022-07-21_00-05-rootfs.tar.zst
# SHA256SUM=5d794ab799cb983d9d19233782c71c7f5ed772415baafaa59e6be3cc0b734119
# BUILD_DATE=20220721
# BUILD_TAG=2022-07-21
# STATUS=completed
# VERSION=latest02
# END_TIME=00:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-21
begin = 2022-07-21 00:02:26.094957706+00:00
start-sync_0 = 00:03:49
start-zstd = 00:05:12
start-sync_1 = 00:05:35
end-sync_1 = 00:05:45
end = 2022-07-21 00:05:45.219913116+00:00

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
