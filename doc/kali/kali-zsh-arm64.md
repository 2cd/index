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
tag = ["zsh", "2022-02-24"]
os = "kali"
release = "rolling"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "kali-zsh_arm64_2022-02-24_12-20.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "6ca2ed2a2b3e00e7f0f70c0d43923492d3c152fd5a2748b0f96d1d8c3b90b0ea"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "730M"
tar_bytes = 765309440

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "142M"
zstd_bytes = 148400914

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220217"
previous_tag = "2022-02-17"
previous_file = "kali-zsh_arm64_2022-02-17_12-20-rootfs.tar.zst"
previous_sha256 = "1ad9ab77b6a52d1b72e2aaf0a07e76777cc16292f7ac57e3b6c46fbfdb32cc3a"

current_version = "latest02"
current_date = "20220224"
old_file = "kali-zsh_arm64_2022-02-10_12-20-rootfs.tar.zst"
old_sha256 = "37c8bc3f56a0919351c02cc3d295e58e691b15e305c89776b9bd381665d9ad71"
# edition 2021
# DISTRO_NAME=kali-rolling_arm64
# ROOTFS_FILE=kali-zsh_arm64_2022-02-24_12-20-rootfs.tar.zst
# SHA256SUM=6ca2ed2a2b3e00e7f0f70c0d43923492d3c152fd5a2748b0f96d1d8c3b90b0ea
# BUILD_DATE=20220224
# BUILD_TAG=2022-02-24
# STATUS=completed
# VERSION=latest02
# END_TIME=12:20

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-24
begin = 2022-02-24 12:02:36.624937082+00:00
start-sync_0 = 12:15:51
start-zstd = 12:17:48
start-sync_1 = 12:20:21
end-sync_1 = 12:20:38
end = 2022-02-24 12:20:38.304716271+00:00

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
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
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
ldd = 'ldd (Debian GLIBC 2.33-6) 2.33'
zsh = 'zsh 5.8.1 (aarch64-unknown-linux-gnu)'
```
