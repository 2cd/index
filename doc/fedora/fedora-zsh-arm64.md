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
tag = ["zsh", "2023-01-03"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-zsh_arm64_2023-01-03_12-41.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "06d5dd3709506563d99eddcf79105116a291a7ac50d12687d84966bc9a408e3f"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.4G"
tar_bytes = 1478596096

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "211M"
zstd_bytes = 220702569

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221227"
previous_tag = "2022-12-27"
previous_file = "fedora-zsh_arm64_2022-12-27_12-44-rootfs.tar.zst"
previous_sha256 = "028755105946e23f30737429a5701b67cd87db254f065a2a12bdd05178e512f9"

current_version = "latest02"
current_date = "20230103"
old_file = "fedora-zsh_arm64_2022-12-20_12-48-rootfs.tar.zst"
old_sha256 = "5a1e48c83f1a0e462a53716e7ecbebe2b7da04c6d6fb9821bd43e96fa233c687"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-zsh_arm64_2023-01-03_12-41-rootfs.tar.zst
# SHA256SUM=06d5dd3709506563d99eddcf79105116a291a7ac50d12687d84966bc9a408e3f
# BUILD_DATE=20230103
# BUILD_TAG=2023-01-03
# STATUS=completed
# VERSION=latest02
# END_TIME=12:41

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-03
begin = 2023-01-03 12:02:25.499437191+00:00
start-sync_0 = 12:35:00
start-zstd = 12:37:01
start-sync_1 = 12:41:02
end-sync_1 = 12:41:22
end = 2023-01-03 12:41:22.022096782+00:00

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
ldd = 'ldd (GNU libc) 2.36.9000'
zsh = 'zsh 5.9 (aarch64-redhat-linux-gnu)'
```
