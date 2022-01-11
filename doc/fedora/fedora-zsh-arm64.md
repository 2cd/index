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
tag = ["zsh", "2022-01-11"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "fedora-zsh_arm64_2022-01-11_12-45.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "8f2d538a1b7c1f97dd4d549a2ee0e9d2f8bc687a2afd8a5611eeb8581960b363"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "985M"
tar_bytes = 1032300544

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "158M"
zstd_bytes = 164776355

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220104"
previous_tag = "2022-01-04"
previous_file = "fedora-zsh_arm64_2022-01-04_12-49-rootfs.tar.zst"
previous_sha256 = "5ed5274e47255e1294d8ee67a867ede24aede679dbad320b88a1bffed8a8ba5f"

current_version = "latest02"
current_date = "20220111"
old_file = "fedora-zsh_arm64_2021-12-28_12-40-rootfs.tar.zst"
old_sha256 = "9f6f881382b83bf8be610dac3c8083216d7884a8cb73ed672da187303e8a51cb"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-zsh_arm64_2022-01-11_12-45-rootfs.tar.zst
# SHA256SUM=8f2d538a1b7c1f97dd4d549a2ee0e9d2f8bc687a2afd8a5611eeb8581960b363
# BUILD_DATE=20220111
# BUILD_TAG=2022-01-11
# STATUS=completed
# VERSION=latest02
# END_TIME=12:45

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-11
begin = 2022-01-11 12:02:32.207611762+00:00
start-sync_0 = 12:39:08
start-zstd = 12:41:19
start-sync_1 = 12:44:40
end-sync_1 = 12:45:05
end = 2022-01-11 12:45:05.864851898+00:00

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
