# alpine-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name alpine-zsh-arm64 \
    cake233/alpine-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it alpine-zsh-arm64 zsh
```

## alpine-zsh-arm64.toml

```toml
[main]
name = "alpine"
tag = ["zsh", "2023-06-08"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_arm64_2023-06-08_00-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b4b904bb7b235839f3b0a91800cd65bc25c43e58646470f911c176ff352f663e"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "112M"
tar_bytes = 116566016

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "31M"
zstd_bytes = 31601511

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230601"
previous_tag = "2023-06-01"
previous_file = "alpine-zsh_arm64_2023-06-01_00-05-rootfs.tar.zst"
previous_sha256 = "47c1c636d659300ad80c2db43b5b77efcbd28706363d85d0fa45ead23ea3f226"

current_version = "latest01"
current_date = "20230608"
old_file = "alpine-zsh_arm64_2023-05-25_00-05-rootfs.tar.zst"
old_sha256 = "c0f46a76dbc2acbb90ec2fa2ce554cc95f02abbbdf50a0d0d9d1b39ddb91aea5"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-zsh_arm64_2023-06-08_00-05-rootfs.tar.zst
# SHA256SUM=b4b904bb7b235839f3b0a91800cd65bc25c43e58646470f911c176ff352f663e
# BUILD_DATE=20230608
# BUILD_TAG=2023-06-08
# STATUS=completed
# VERSION=latest01
# END_TIME=00:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-08
begin = 2023-06-08 00:02:29.362549388+00:00
start-sync_0 = 00:03:53
start-zstd = 00:05:14
start-sync_1 = 00:05:46
end-sync_1 = 00:05:52
end = 2023-06-08 00:05:52.388811400+00:00

[server]
repo = "cake233/alpine-zsh-arm64"

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
ldd = 'musl libc (aarch64) Version 1.2.4'
zsh = 'zsh 5.9 (aarch64-alpine-linux-musl)'
```
