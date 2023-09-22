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
tag = ["zsh", "2023-09-22"]
os = "manjaro"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-zsh_arm64_2023-09-22_12-14.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "59b919f3acede4f8e8be332184734e9eab93e8cbd014fe08ad6b201790e60ba3"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.2G"
tar_bytes = 1210945024

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "259M"
zstd_bytes = 270685555

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230915"
previous_tag = "2023-09-15"
previous_file = "manjaro-zsh_arm64_2023-09-15_12-20-rootfs.tar.zst"
previous_sha256 = "cdbbd67a62a618b8c90d7c9f431fe677b959550d78345f1192189c3a5ad7050f"

current_version = "latest01"
current_date = "20230922"
old_file = "manjaro-zsh_arm64_2023-09-08_12-19-rootfs.tar.zst"
old_sha256 = "fdd087f841e393358750ed4b5cf3dc782fcf3a02be74923036dba3bd3afadebb"
# edition 2021
# DISTRO_NAME=manjaro-stable_arm64
# ROOTFS_FILE=manjaro-zsh_arm64_2023-09-22_12-14-rootfs.tar.zst
# SHA256SUM=59b919f3acede4f8e8be332184734e9eab93e8cbd014fe08ad6b201790e60ba3
# BUILD_DATE=20230922
# BUILD_TAG=2023-09-22
# STATUS=completed
# VERSION=latest01
# END_TIME=12:14

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-22
begin = 2023-09-22 12:02:34.112039190+00:00
start-sync_0 = 12:07:25
start-zstd = 12:09:05
start-sync_1 = 12:13:39
end-sync_1 = 12:14:03
end = 2023-09-22 12:14:03.117852932+00:00

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
