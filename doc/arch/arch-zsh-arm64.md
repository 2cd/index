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
tag = ["zsh", "2023-08-30"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-zsh_arm64_2023-08-30_00-44.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "78eafb884cae09ec229033c98ece18ad927acf876a3e2f6359d4421589fb79ee"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1080444416

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "242M"
zstd_bytes = 253177925

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230823"
previous_tag = "2023-08-23"
previous_file = "arch-zsh_arm64_2023-08-23_00-41-rootfs.tar.zst"
previous_sha256 = "bf5da640d44626d9e9c27aee8accd4b2a27043ae290871e2789833ded0c5f068"

current_version = "latest01"
current_date = "20230830"
old_file = "arch-zsh_arm64_2023-08-16_00-26-rootfs.tar.zst"
old_sha256 = "050afb5df36f45e574a6794d4b058b9b24933e3537149020380fbcfe7d0a7dbd"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-zsh_arm64_2023-08-30_00-44-rootfs.tar.zst
# SHA256SUM=78eafb884cae09ec229033c98ece18ad927acf876a3e2f6359d4421589fb79ee
# BUILD_DATE=20230830
# BUILD_TAG=2023-08-30
# STATUS=completed
# VERSION=latest01
# END_TIME=00:44

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-30
begin = 2023-08-30 00:09:52.864268531+00:00
start-sync_0 = 00:37:43
start-zstd = 00:39:18
start-sync_1 = 00:44:16
end-sync_1 = 00:44:40
end = 2023-08-30 00:44:40.875313812+00:00

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