# manjaro-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name manjaro-zsh-arm64 \
    cake233/manjaro-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it manjaro-zsh-arm64 zsh
```

## manjaro-zsh-arm64.toml

```toml
[main]
name = "manjaro"
tag = ["zsh", "2023-03-24"]
os = "manjaro"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-zsh_arm64_2023-03-24_12-22.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "307f5375586992861537579d1713cdbf2803a3f973031ce72b79e79acc252afd"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1161656320

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "253M"
zstd_bytes = 265282396

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230317"
previous_tag = "2023-03-17"
previous_file = "manjaro-zsh_arm64_2023-03-17_12-19-rootfs.tar.zst"
previous_sha256 = "d319d630138093d320569866f1227b1f21945f9af21d3cb162b697fe85e62213"

current_version = "latest01"
current_date = "20230324"
old_file = "manjaro-zsh_arm64_2023-03-10_12-19-rootfs.tar.zst"
old_sha256 = "b2ace66146cb9422b411c4cb06606654a7a7bc3e9e32ffcd641e217efd99e119"
# edition 2021
# DISTRO_NAME=manjaro-stable_arm64
# ROOTFS_FILE=manjaro-zsh_arm64_2023-03-24_12-22-rootfs.tar.zst
# SHA256SUM=307f5375586992861537579d1713cdbf2803a3f973031ce72b79e79acc252afd
# BUILD_DATE=20230324
# BUILD_TAG=2023-03-24
# STATUS=completed
# VERSION=latest01
# END_TIME=12:22

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-24
begin = 2023-03-24 12:02:30.789296943+00:00
start-sync_0 = 12:15:24
start-zstd = 12:17:10
start-sync_1 = 12:22:07
end-sync_1 = 12:22:31
end = 2023-03-24 12:22:31.619707674+00:00

[server]
repo = "cake233/manjaro-zsh-arm64"

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
LANG = "en_US.UTF-8"

[version]
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'
```
