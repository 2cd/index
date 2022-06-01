# arch-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name arch-zsh-arm64 \
    cake233/arch-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it arch-zsh-arm64 zsh
```

## arch-zsh-arm64.toml

```toml
[main]
name = "arch"
tag = ["zsh", "2022-06-01"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-zsh_arm64_2022-06-01_00-29.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "2c698793825c469a6db9edd4e64a3bdb23edc9410ca65f76a658cf793741f672"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "952M"
tar_bytes = 997853184

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "225M"
zstd_bytes = 235242161

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220525"
previous_tag = "2022-05-25"
previous_file = "arch-zsh_arm64_2022-05-25_00-25-rootfs.tar.zst"
previous_sha256 = "2520a6e99723a4afd51c79fe00bcb9a0f602ff7a5f934d83cda36e061b4beaf4"

current_version = "latest02"
current_date = "20220601"
old_file = "arch-zsh_arm64_2022-05-18_00-25-rootfs.tar.zst"
old_sha256 = "0c4e874794da563f655792d47b124d8b9fe4df45cbf6cf213ee2942d4de145c1"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-zsh_arm64_2022-06-01_00-29-rootfs.tar.zst
# SHA256SUM=2c698793825c469a6db9edd4e64a3bdb23edc9410ca65f76a658cf793741f672
# BUILD_DATE=20220601
# BUILD_TAG=2022-06-01
# STATUS=completed
# VERSION=latest02
# END_TIME=00:29

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-01
begin = 2022-06-01 00:08:51.484107363+00:00
start-sync_0 = 00:23:36
start-zstd = 00:25:08
start-sync_1 = 00:29:04
end-sync_1 = 00:29:26
end = 2022-06-01 00:29:26.909951860+00:00

[server]
repo = "cake233/arch-zsh-arm64"

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
