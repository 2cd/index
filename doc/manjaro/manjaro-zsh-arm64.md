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
tag = ["zsh", "2023-12-22"]
os = "manjaro"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-zsh_arm64_2023-12-22_12-17.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "08ecb37fef24ebcdfed1eecc3b7ea37a560bca4b12b7275cad18d77a815e1107"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.2G"
tar_bytes = 1214285312

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "261M"
zstd_bytes = 273233707

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231124"
previous_tag = "2023-11-24"
previous_file = "manjaro-zsh_arm64_2023-11-24_12-17-rootfs.tar.zst"
previous_sha256 = "f258d731770e5f7b1a64465f6ef7841b2267142832b2c8ecfa6b9a18ca610419"

current_version = "latest02"
current_date = "20231222"
old_file = "manjaro-zsh_arm64_2023-11-17_12-21-rootfs.tar.zst"
old_sha256 = "45cf055520e83c887e84db58df2bc0c9ca89b7b9c9ae294fce45b10a4831a1e6"
# edition 2021
# DISTRO_NAME=manjaro-stable_arm64
# ROOTFS_FILE=manjaro-zsh_arm64_2023-12-22_12-17-rootfs.tar.zst
# SHA256SUM=08ecb37fef24ebcdfed1eecc3b7ea37a560bca4b12b7275cad18d77a815e1107
# BUILD_DATE=20231222
# BUILD_TAG=2023-12-22
# STATUS=completed
# VERSION=latest02
# END_TIME=12:17

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-12-22
begin = 2023-12-22 12:02:32.779397341+00:00
start-sync_0 = 12:11:36
start-zstd = 12:13:11
start-sync_1 = 12:17:19
end-sync_1 = 12:17:35
end = 2023-12-22 12:17:35.921253015+00:00

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
