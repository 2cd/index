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
tag = ["zsh", "2023-03-23"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_arm64_2023-03-23_00-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "344c146dd7372bba6f54bfeb68b12331f0a890d719e77f62271ba203fde0bfb5"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "109M"
tar_bytes = 114072576

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "31M"
zstd_bytes = 32255739

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230316"
previous_tag = "2023-03-16"
previous_file = "alpine-zsh_arm64_2023-03-16_00-06-rootfs.tar.zst"
previous_sha256 = "9f28aca3a297e64080ecad7f98cd13a299e148ffcff895d287e4611e2c819fb4"

current_version = "latest02"
current_date = "20230323"
old_file = "alpine-zsh_arm64_2023-03-09_00-05-rootfs.tar.zst"
old_sha256 = "af83b564ff8da77aef5053fa09c15c5c51970d955c96e4aa0b146d36df268237"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-zsh_arm64_2023-03-23_00-06-rootfs.tar.zst
# SHA256SUM=344c146dd7372bba6f54bfeb68b12331f0a890d719e77f62271ba203fde0bfb5
# BUILD_DATE=20230323
# BUILD_TAG=2023-03-23
# STATUS=completed
# VERSION=latest02
# END_TIME=00:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-23
begin = 2023-03-23 00:02:41.973212203+00:00
start-sync_0 = 00:04:29
start-zstd = 00:05:54
start-sync_1 = 00:06:30
end-sync_1 = 00:06:41
end = 2023-03-23 00:06:41.685398117+00:00

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
ldd = 'musl libc (aarch64) Version 1.2.3'
zsh = 'zsh 5.9 (aarch64-alpine-linux-musl)'
```
