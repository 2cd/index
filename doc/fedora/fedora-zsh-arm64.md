# fedora-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name fedora-zsh-arm64 \
    cake233/fedora-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it fedora-zsh-arm64 zsh
```

## fedora-zsh-arm64.toml

```toml
[main]
name = "fedora"
tag = ["zsh", "2021-12-21"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "fedora-zsh_arm64_2021-12-21_12-48.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "b983df4e17978640ae73d628ec8e39fbc76e28918ef41c896c1469631eeb41a1"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "983M"
tar_bytes = 1030588928

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "157M"
zstd_bytes = 164380078

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211214"
previous_tag = "2021-12-14"
previous_file = "fedora-zsh_arm64_2021-12-14_12-55-rootfs.tar.zst"
previous_sha256 = "684d79bb7fad9b8679dc2b8eb069d45df3b108a7e8c6229ef4bfdee93be4a9a7"

current_version = "latest01"
current_date = "20211221"
old_file = "fedora-zsh_arm64_2021-12-07_12-39-rootfs.tar.zst"
old_sha256 = "4fcc5bfab6c6b15395fc104cc48ce30fba7edb94cbd7de712eedde84e6b19203"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-zsh_arm64_2021-12-21_12-48-rootfs.tar.zst
# SHA256SUM=b983df4e17978640ae73d628ec8e39fbc76e28918ef41c896c1469631eeb41a1
# BUILD_DATE=20211221
# BUILD_TAG=2021-12-21
# STATUS=completed
# VERSION=latest01
# END_TIME=12:48

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-21
begin = 2021-12-21 12:02:28.956017180+00:00
start-sync_0 = 12:42:36
start-zstd = 12:44:50
start-sync_1 = 12:48:15
end-sync_1 = 12:48:45
end = 2021-12-21 12:48:45.337373300+00:00

[server]
repo = "cake233/fedora-zsh-arm64"

[server.node1]
name = "cn"
current = false
previous = false
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
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
ldd = 'ldd (GNU libc) 2.34.9000'
zsh = 'zsh 5.8 (aarch64-redhat-linux-gnu)'
```
