# kali-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name kali-zsh-arm64 \
    cake233/kali-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it kali-zsh-arm64 zsh
```

## kali-zsh-arm64.toml

```toml
[main]
name = "kali"
tag = ["zsh", "2023-12-28"]
os = "kali"
release = "rolling"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-zsh_arm64_2023-12-28_12-31.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "2b6dddc28424d070df538b2816035b7204dd727ee2a801b3f8b4741b0c888dd8"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "825M"
tar_bytes = 864396800

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "150M"
zstd_bytes = 157234877

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231123"
previous_tag = "2023-11-23"
previous_file = "kali-zsh_arm64_2023-11-23_12-37-rootfs.tar.zst"
previous_sha256 = "d4f8b5b9186566af73af5cf62cb2060e9bda8e6053879be0e9dea16fd2dd7e9b"

current_version = "latest02"
current_date = "20231228"
old_file = "kali-zsh_arm64_2023-11-16_12-32-rootfs.tar.zst"
old_sha256 = "c89b54f3e9c861df3f03d3d8b812faf1fe58e2326720594cdbd0542b0e9ef794"
# edition 2021
# DISTRO_NAME=kali-rolling_arm64
# ROOTFS_FILE=kali-zsh_arm64_2023-12-28_12-31-rootfs.tar.zst
# SHA256SUM=2b6dddc28424d070df538b2816035b7204dd727ee2a801b3f8b4741b0c888dd8
# BUILD_DATE=20231228
# BUILD_TAG=2023-12-28
# STATUS=completed
# VERSION=latest02
# END_TIME=12:31

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-12-28
begin = 2023-12-28 12:02:28.639404871+00:00
start-sync_0 = 12:27:30
start-zstd = 12:29:06
start-sync_1 = 12:31:17
end-sync_1 = 12:31:28
end = 2023-12-28 12:31:28.266172669+00:00

[server]
repo = "cake233/kali-zsh-arm64"

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
ldd = 'ldd (Debian GLIBC 2.37-12) 2.37'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'
```
