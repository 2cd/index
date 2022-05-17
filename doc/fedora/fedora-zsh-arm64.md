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
tag = ["zsh", "2022-05-17"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-zsh_arm64_2022-05-17_12-43.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "45e83b120daca245336094d0f61fd2d38dc971a4646eb602d02e9cd05213de76"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "976M"
tar_bytes = 1023270400

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "157M"
zstd_bytes = 163757389

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220510"
previous_tag = "2022-05-10"
previous_file = "fedora-zsh_arm64_2022-05-10_12-57-rootfs.tar.zst"
previous_sha256 = "ca4f5518f7ac1316ebce7619d84a3b8680ff3ace59744e33d43e6dcb2b736162"

current_version = "latest02"
current_date = "20220517"
old_file = "fedora-zsh_arm64_2022-05-03_12-35-rootfs.tar.zst"
old_sha256 = "98c36003237882d63ad8c208b239b960a17570b0b5b2f30fe6555b6bbf57a64b"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-zsh_arm64_2022-05-17_12-43-rootfs.tar.zst
# SHA256SUM=45e83b120daca245336094d0f61fd2d38dc971a4646eb602d02e9cd05213de76
# BUILD_DATE=20220517
# BUILD_TAG=2022-05-17
# STATUS=completed
# VERSION=latest02
# END_TIME=12:43

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-17
begin = 2022-05-17 12:02:31.534284662+00:00
start-sync_0 = 12:37:36
start-zstd = 12:39:31
start-sync_1 = 12:42:44
end-sync_1 = 12:43:01
end = 2022-05-17 12:43:01.510263386+00:00

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
ldd = 'ldd (GNU libc) 2.35.9000'
zsh = 'zsh 5.9 (aarch64-redhat-linux-gnu)'
```
