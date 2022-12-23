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
tag = ["zsh", "2022-12-23"]
os = "manjaro"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-zsh_arm64_2022-12-23_12-20.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "3467448c66955079f127e89431186153eb7edf1f3bc8810cfd13e797b76b4771"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1136183296

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "249M"
zstd_bytes = 260932700

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221216"
previous_tag = "2022-12-16"
previous_file = "manjaro-zsh_arm64_2022-12-16_12-20-rootfs.tar.zst"
previous_sha256 = "0197a01ea66d7350a26fda2729d1a07faa5a7cd9a6540a91f2b91033315c743f"

current_version = "latest02"
current_date = "20221223"
old_file = "manjaro-zsh_arm64_2022-10-28_12-20-rootfs.tar.zst"
old_sha256 = "60af8dea6c454cd65d828037615d5088cf609b393d6e4c55222ea25b44afa13c"
# edition 2021
# DISTRO_NAME=manjaro-stable_arm64
# ROOTFS_FILE=manjaro-zsh_arm64_2022-12-23_12-20-rootfs.tar.zst
# SHA256SUM=3467448c66955079f127e89431186153eb7edf1f3bc8810cfd13e797b76b4771
# BUILD_DATE=20221223
# BUILD_TAG=2022-12-23
# STATUS=completed
# VERSION=latest02
# END_TIME=12:20

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-23
begin = 2022-12-23 12:02:31.553366543+00:00
start-sync_0 = 12:14:09
start-zstd = 12:15:48
start-sync_1 = 12:19:50
end-sync_1 = 12:20:09
end = 2022-12-23 12:20:09.612624565+00:00

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
