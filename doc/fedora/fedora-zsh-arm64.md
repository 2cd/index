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
tag = ["zsh", "2022-03-22"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "fedora-zsh_arm64_2022-03-22_12-37.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "1df220d8e730861cf3c1664c01d004d241895cea7135f616dcc87c94421bc575"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "981M"
tar_bytes = 1028397568

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "156M"
zstd_bytes = 163443476

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220315"
previous_tag = "2022-03-15"
previous_file = "fedora-zsh_arm64_2022-03-15_12-48-rootfs.tar.zst"
previous_sha256 = "50b164f9d35ea9cbeebd652982d6efa887f0f87b6ed9ec8595c058261b473f4b"

current_version = "latest02"
current_date = "20220322"
old_file = "fedora-zsh_arm64_2022-03-08_12-35-rootfs.tar.zst"
old_sha256 = "89b1627da33be5d15edb4c923a2b895668566b6b2635064266d5501dd91e9965"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-zsh_arm64_2022-03-22_12-37-rootfs.tar.zst
# SHA256SUM=1df220d8e730861cf3c1664c01d004d241895cea7135f616dcc87c94421bc575
# BUILD_DATE=20220322
# BUILD_TAG=2022-03-22
# STATUS=completed
# VERSION=latest02
# END_TIME=12:37

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-22
begin = 2022-03-22 12:02:34.445323448+00:00
start-sync_0 = 12:32:18
start-zstd = 12:34:12
start-sync_1 = 12:37:17
end-sync_1 = 12:37:34
end = 2022-03-22 12:37:34.538676102+00:00

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
ldd = 'ldd (GNU libc) 2.35.9000'
zsh = 'zsh 5.8.1 (aarch64-redhat-linux-gnu)'
```
