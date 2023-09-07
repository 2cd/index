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
tag = ["zsh", "2023-09-07"]
os = "alpine"
release = "edge"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_armhf_2023-09-07_00-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "1691ebe568060caeb89cabe8397080e6e6947c652cae3fc2d62a72df6daea3c3"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "107M"
tar_bytes = 111370240

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "35M"
zstd_bytes = 36661206

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230831"
previous_tag = "2023-08-31"
previous_file = "alpine-zsh_armhf_2023-08-31_00-06-rootfs.tar.zst"
previous_sha256 = "5f073397f19a0fbac6ef9f768c67ffee9923d3192e9b27252e63073a595664b0"

current_version = "latest02"
current_date = "20230907"
old_file = "alpine-zsh_armhf_2023-08-24_00-06-rootfs.tar.zst"
old_sha256 = "3fda922fbe1a5334c1f6ca0b990e08f2f101b58f1839d43e03b2e3ec08d378af"
# edition 2021
# DISTRO_NAME=alpine-edge_armhf
# ROOTFS_FILE=alpine-zsh_armhf_2023-09-07_00-06-rootfs.tar.zst
# SHA256SUM=1691ebe568060caeb89cabe8397080e6e6947c652cae3fc2d62a72df6daea3c3
# BUILD_DATE=20230907
# BUILD_TAG=2023-09-07
# STATUS=completed
# VERSION=latest02
# END_TIME=00:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-07
begin = 2023-09-07 00:02:40.605965096+00:00
start-sync_0 = 00:04:23
start-zstd = 00:05:48
start-sync_1 = 00:06:27
end-sync_1 = 00:06:37
end = 2023-09-07 00:06:37.539987366+00:00

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
