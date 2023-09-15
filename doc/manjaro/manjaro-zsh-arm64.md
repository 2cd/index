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
tag = ["zsh", "2023-09-15"]
os = "manjaro"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-zsh_arm64_2023-09-15_12-20.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "cdbbd67a62a618b8c90d7c9f431fe677b959550d78345f1192189c3a5ad7050f"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.2G"
tar_bytes = 1213704192

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "260M"
zstd_bytes = 271934414

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230908"
previous_tag = "2023-09-08"
previous_file = "manjaro-zsh_arm64_2023-09-08_12-19-rootfs.tar.zst"
previous_sha256 = "fdd087f841e393358750ed4b5cf3dc782fcf3a02be74923036dba3bd3afadebb"

current_version = "latest02"
current_date = "20230915"
old_file = "manjaro-zsh_arm64_2023-09-01_12-25-rootfs.tar.zst"
old_sha256 = "d3cf7dd53fac60998ed00a774dae001a77afe7d79ff34c82eb769f1ffd9e20c1"
# edition 2021
# DISTRO_NAME=manjaro-stable_arm64
# ROOTFS_FILE=manjaro-zsh_arm64_2023-09-15_12-20-rootfs.tar.zst
# SHA256SUM=cdbbd67a62a618b8c90d7c9f431fe677b959550d78345f1192189c3a5ad7050f
# BUILD_DATE=20230915
# BUILD_TAG=2023-09-15
# STATUS=completed
# VERSION=latest02
# END_TIME=12:20

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-15
begin = 2023-09-15 12:02:35.384909527+00:00
start-sync_0 = 12:13:36
start-zstd = 12:15:16
start-sync_1 = 12:19:56
end-sync_1 = 12:20:21
end = 2023-09-15 12:20:21.128898233+00:00

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
