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
tag = ["zsh", "2023-01-24"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-zsh_arm64_2023-01-24_12-51.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "7ad20eef6a74545dc96e24aed1fa19856db7023cac318182e97411ad10be9811"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.4G"
tar_bytes = 1487967744

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "212M"
zstd_bytes = 222251005

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230117"
previous_tag = "2023-01-17"
previous_file = "fedora-zsh_arm64_2023-01-17_12-51-rootfs.tar.zst"
previous_sha256 = "4c469f28b5f16e82d9060502c69d7e83c50d90ca1e33c2f8a407b303fb512681"

current_version = "latest01"
current_date = "20230124"
old_file = "fedora-zsh_arm64_2023-01-10_12-41-rootfs.tar.zst"
old_sha256 = "45ec8180106b548446e8869cbf8fe7a229189858a12e322d9d069f7e88dc9afc"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-zsh_arm64_2023-01-24_12-51-rootfs.tar.zst
# SHA256SUM=7ad20eef6a74545dc96e24aed1fa19856db7023cac318182e97411ad10be9811
# BUILD_DATE=20230124
# BUILD_TAG=2023-01-24
# STATUS=completed
# VERSION=latest01
# END_TIME=12:51

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-24
begin = 2023-01-24 12:02:29.055664737+00:00
start-sync_0 = 12:44:54
start-zstd = 12:47:08
start-sync_1 = 12:51:14
end-sync_1 = 12:51:35
end = 2023-01-24 12:51:35.609648459+00:00

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
