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
tag = ["zsh", "2023-09-01"]
os = "manjaro"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-zsh_arm64_2023-09-01_12-25.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d3cf7dd53fac60998ed00a774dae001a77afe7d79ff34c82eb769f1ffd9e20c1"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.2G"
tar_bytes = 1201615360

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "258M"
zstd_bytes = 270134213

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230825"
previous_tag = "2023-08-25"
previous_file = "manjaro-zsh_arm64_2023-08-25_12-20-rootfs.tar.zst"
previous_sha256 = "f2c215dec9333ec583a6ca89f14da099641949adf2257e29c3c3de321f0d5fe5"

current_version = "latest02"
current_date = "20230901"
old_file = "manjaro-zsh_arm64_2023-08-18_12-26-rootfs.tar.zst"
old_sha256 = "30270c389f32edda7cfc78fb45df8c0e50f7d8a261b394092476490fdfb123fe"
# edition 2021
# DISTRO_NAME=manjaro-stable_arm64
# ROOTFS_FILE=manjaro-zsh_arm64_2023-09-01_12-25-rootfs.tar.zst
# SHA256SUM=d3cf7dd53fac60998ed00a774dae001a77afe7d79ff34c82eb769f1ffd9e20c1
# BUILD_DATE=20230901
# BUILD_TAG=2023-09-01
# STATUS=completed
# VERSION=latest02
# END_TIME=12:25

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-01
begin = 2023-09-01 12:02:38.003753264+00:00
start-sync_0 = 12:18:13
start-zstd = 12:19:56
start-sync_1 = 12:25:10
end-sync_1 = 12:25:36
end = 2023-09-01 12:25:36.765417650+00:00

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
