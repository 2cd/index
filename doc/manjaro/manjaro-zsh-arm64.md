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
tag = ["zsh", "2023-12-15"]
os = "manjaro"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-zsh_arm64_2023-12-15_12-16.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "dd46c3f5aad50a861961da78210505c474289d80b00fa192de51e0ba1c2514c4"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.2G"
tar_bytes = 1214254592

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "261M"
zstd_bytes = 273155045

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231124"
previous_tag = "2023-11-24"
previous_file = "manjaro-zsh_arm64_2023-11-24_12-17-rootfs.tar.zst"
previous_sha256 = "f258d731770e5f7b1a64465f6ef7841b2267142832b2c8ecfa6b9a18ca610419"

current_version = "latest02"
current_date = "20231215"
old_file = "manjaro-zsh_arm64_2023-11-17_12-21-rootfs.tar.zst"
old_sha256 = "45cf055520e83c887e84db58df2bc0c9ca89b7b9c9ae294fce45b10a4831a1e6"
# edition 2021
# DISTRO_NAME=manjaro-stable_arm64
# ROOTFS_FILE=manjaro-zsh_arm64_2023-12-15_12-16-rootfs.tar.zst
# SHA256SUM=dd46c3f5aad50a861961da78210505c474289d80b00fa192de51e0ba1c2514c4
# BUILD_DATE=20231215
# BUILD_TAG=2023-12-15
# STATUS=completed
# VERSION=latest02
# END_TIME=12:16

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-12-15
begin = 2023-12-15 12:02:30.432208614+00:00
start-sync_0 = 12:11:22
start-zstd = 12:12:58
start-sync_1 = 12:16:43
end-sync_1 = 12:16:59
end = 2023-12-15 12:16:59.731789740+00:00

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
