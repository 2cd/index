# debian-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name debian-zsh-arm64 \
    cake233/debian-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it debian-zsh-arm64 zsh
```

## debian-zsh-arm64.toml

```toml
[main]
name = "debian"
tag = ["zsh", "2022-04-20"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false
syntax_version = "0.0.0-alpha.3"

[file]
name = "debian-zsh_arm64_2022-04-20_12-17.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "4b98bac766eced670d891f2439b49116c9908139aaea416787119e7998daa68f"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "738M"
tar_bytes = 773797376

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "143M"
zstd_bytes = 149755433

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220413"
previous_tag = "2022-04-13"
previous_file = "debian-zsh_arm64_2022-04-13_12-17-rootfs.tar.zst"
previous_sha256 = "4cf43ccc5a6bb42c0812c1a5fc02ddfce0e6fb35c6f568509ee42c3f46dd9471"

current_version = "latest02"
current_date = "20220420"
old_file = "debian-zsh_arm64_2022-04-06_11-32-rootfs.tar.zst"
old_sha256 = "eefa37c43801a3cc658d98ea93f0072e58a1ea18416790f687e2c89cc9b00a94"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-zsh_arm64_2022-04-20_12-17-rootfs.tar.zst
# SHA256SUM=4b98bac766eced670d891f2439b49116c9908139aaea416787119e7998daa68f
# BUILD_DATE=20220420
# BUILD_TAG=2022-04-20
# STATUS=completed
# VERSION=latest02
# END_TIME=12:17

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-20
begin = 2022-04-20 12:02:32.423474725+00:00
start-sync_0 = 12:13:33
start-zstd = 12:15:14
start-sync_1 = 12:17:35
end-sync_1 = 12:17:48
end = 2022-04-20 12:17:48.449861558+00:00

[server]
repo = "cake233/debian-zsh-arm64"

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
ldd = 'ldd (Debian GLIBC 2.33-7) 2.33'
zsh = 'zsh 5.8.1 (aarch64-unknown-linux-gnu)'
```
