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
tag = ["zsh", "2023-04-04"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-zsh_arm64_2023-04-04_12-55.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "73cb8014175ceabf0a6a8101e0d2f1f0b35456e2ad978c5206252b7026f47a1d"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1539888640

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "218M"
zstd_bytes = 228087205

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230328"
previous_tag = "2023-03-28"
previous_file = "fedora-zsh_arm64_2023-03-28_12-59-rootfs.tar.zst"
previous_sha256 = "cb132a89fe9a5f31df200e2da9d0a8e4f63d5486ee55dcb5676a0f69d29b52b8"

current_version = "latest01"
current_date = "20230404"
old_file = "fedora-zsh_arm64_2023-03-21_12-55-rootfs.tar.zst"
old_sha256 = "6aa42d6e0e31721b0458747146cc26ee23a8575fbbbff18a6a415a95d95f6988"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-zsh_arm64_2023-04-04_12-55-rootfs.tar.zst
# SHA256SUM=73cb8014175ceabf0a6a8101e0d2f1f0b35456e2ad978c5206252b7026f47a1d
# BUILD_DATE=20230404
# BUILD_TAG=2023-04-04
# STATUS=completed
# VERSION=latest01
# END_TIME=12:55

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-04
begin = 2023-04-04 12:02:37.299758517+00:00
start-sync_0 = 12:48:39
start-zstd = 12:50:48
start-sync_1 = 12:54:57
end-sync_1 = 12:55:16
end = 2023-04-04 12:55:16.600006519+00:00

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
