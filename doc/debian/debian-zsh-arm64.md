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
tag = ["zsh", "2022-12-07"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_arm64_2022-12-07_12-17.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "1ccb9c5333e8bc309057b997be451ab7bdc6a361ef18e8155f4df11988d09241"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "805M"
tar_bytes = 843389440

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "146M"
zstd_bytes = 152561216

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221130"
previous_tag = "2022-11-30"
previous_file = "debian-zsh_arm64_2022-11-30_12-17-rootfs.tar.zst"
previous_sha256 = "8e647aaad3054fad3ff6e52188eeea04d38f06411ec09205a289bf0c4bb7b50e"

current_version = "latest02"
current_date = "20221207"
old_file = "debian-zsh_arm64_2022-11-23_12-17-rootfs.tar.zst"
old_sha256 = "2ffee87a48dd6c7b4f160e13142fb1b507fcab0c9133fc6935f48832477c1196"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-zsh_arm64_2022-12-07_12-17-rootfs.tar.zst
# SHA256SUM=1ccb9c5333e8bc309057b997be451ab7bdc6a361ef18e8155f4df11988d09241
# BUILD_DATE=20221207
# BUILD_TAG=2022-12-07
# STATUS=completed
# VERSION=latest02
# END_TIME=12:17

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-07
begin = 2022-12-07 12:02:29.869091545+00:00
start-sync_0 = 12:12:55
start-zstd = 12:14:44
start-sync_1 = 12:17:12
end-sync_1 = 12:17:28
end = 2022-12-07 12:17:28.659964366+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-6) 2.36'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'
```
