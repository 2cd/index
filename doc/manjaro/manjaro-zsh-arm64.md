# manjaro-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name manjaro-zsh-arm64 \
    cake233/manjaro-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it manjaro-zsh-arm64 zsh
```

## manjaro-zsh-arm64.toml

```toml
[main]
name = "manjaro"
tag = ["zsh", "2024-03-01"]
os = "manjaro"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-zsh_arm64_2024-03-01_12-17.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "4d4712448bf495c632716550eec390305aa42db0d7e89de275a83e0155564a2b"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.2G"
tar_bytes = 1216610304

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "264M"
zstd_bytes = 276478029

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231124"
previous_tag = "2023-11-24"
previous_file = "manjaro-zsh_arm64_2023-11-24_12-17-rootfs.tar.zst"
previous_sha256 = "f258d731770e5f7b1a64465f6ef7841b2267142832b2c8ecfa6b9a18ca610419"

current_version = "latest02"
current_date = "20240301"
old_file = "manjaro-zsh_arm64_2023-11-17_12-21-rootfs.tar.zst"
old_sha256 = "45cf055520e83c887e84db58df2bc0c9ca89b7b9c9ae294fce45b10a4831a1e6"
# edition 2021
# DISTRO_NAME=manjaro-stable_arm64
# ROOTFS_FILE=manjaro-zsh_arm64_2024-03-01_12-17-rootfs.tar.zst
# SHA256SUM=4d4712448bf495c632716550eec390305aa42db0d7e89de275a83e0155564a2b
# BUILD_DATE=20240301
# BUILD_TAG=2024-03-01
# STATUS=completed
# VERSION=latest02
# END_TIME=12:17

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-03-01
begin = 2024-03-01 12:02:34.362030270+00:00
start-sync_0 = 12:11:48
start-zstd = 12:13:24
start-sync_1 = 12:17:34
end-sync_1 = 12:17:51
end = 2024-03-01 12:17:51.160680893+00:00

[server]
repo = "cake233/manjaro-zsh-arm64"

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
