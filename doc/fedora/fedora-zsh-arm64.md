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
tag = ["zsh", "2023-03-14"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-zsh_arm64_2023-03-14_12-57.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "fcb281c470040cfc651b0453accbe2ef0177050d977e206b8c4f3d23740581a6"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1532673024

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "216M"
zstd_bytes = 226413654

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230307"
previous_tag = "2023-03-07"
previous_file = "fedora-zsh_arm64_2023-03-07_13-04-rootfs.tar.zst"
previous_sha256 = "c197830d64f96cec71000701d04ea9fff11175134b0b017f028f87c08e459b40"

current_version = "latest02"
current_date = "20230314"
old_file = "fedora-zsh_arm64_2023-02-28_13-00-rootfs.tar.zst"
old_sha256 = "9bd05c7ec6472952b9ddc822940a24276b7e29b9fe91d35a515c4e3fbbba5d4c"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-zsh_arm64_2023-03-14_12-57-rootfs.tar.zst
# SHA256SUM=fcb281c470040cfc651b0453accbe2ef0177050d977e206b8c4f3d23740581a6
# BUILD_DATE=20230314
# BUILD_TAG=2023-03-14
# STATUS=completed
# VERSION=latest02
# END_TIME=12:57

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-14
begin = 2023-03-14 12:02:34.919724679+00:00
start-sync_0 = 12:50:18
start-zstd = 12:52:32
start-sync_1 = 12:56:54
end-sync_1 = 12:57:17
end = 2023-03-14 12:57:17.339830389+00:00

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
ldd = 'ldd (GNU libc) 2.37.9000'
zsh = 'zsh 5.9 (aarch64-redhat-linux-gnu)'
```
