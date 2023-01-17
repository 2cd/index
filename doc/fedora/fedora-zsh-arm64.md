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
tag = ["zsh", "2023-01-17"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-zsh_arm64_2023-01-17_12-51.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "4c469f28b5f16e82d9060502c69d7e83c50d90ca1e33c2f8a407b303fb512681"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.4G"
tar_bytes = 1486637568

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "212M"
zstd_bytes = 221993127

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230110"
previous_tag = "2023-01-10"
previous_file = "fedora-zsh_arm64_2023-01-10_12-41-rootfs.tar.zst"
previous_sha256 = "45ec8180106b548446e8869cbf8fe7a229189858a12e322d9d069f7e88dc9afc"

current_version = "latest02"
current_date = "20230117"
old_file = "fedora-zsh_arm64_2023-01-03_12-41-rootfs.tar.zst"
old_sha256 = "06d5dd3709506563d99eddcf79105116a291a7ac50d12687d84966bc9a408e3f"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-zsh_arm64_2023-01-17_12-51-rootfs.tar.zst
# SHA256SUM=4c469f28b5f16e82d9060502c69d7e83c50d90ca1e33c2f8a407b303fb512681
# BUILD_DATE=20230117
# BUILD_TAG=2023-01-17
# STATUS=completed
# VERSION=latest02
# END_TIME=12:51

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-17
begin = 2023-01-17 12:02:30.242614510+00:00
start-sync_0 = 12:43:44
start-zstd = 12:45:55
start-sync_1 = 12:50:38
end-sync_1 = 12:51:01
end = 2023-01-17 12:51:01.897724762+00:00

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
