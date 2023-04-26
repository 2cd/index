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
tag = ["zsh", "2023-04-26"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_arm64_2023-04-26_12-24.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8d8af37ef011c975a4b099481ba5c82d8a0a467865f1b83b012bd369438f83af"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "816M"
tar_bytes = 854833152

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "150M"
zstd_bytes = 156234368

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230419"
previous_tag = "2023-04-19"
previous_file = "debian-zsh_arm64_2023-04-19_12-17-rootfs.tar.zst"
previous_sha256 = "d4ee50e29daf8dcd7aefe34896bfbecc24cd7ad6af55c8f7793fbbc03b090936"

current_version = "latest02"
current_date = "20230426"
old_file = "debian-zsh_arm64_2023-04-12_12-17-rootfs.tar.zst"
old_sha256 = "1c3863ed299515350e3ad4cc8590223427cd824c6877cd07e03b09659634bedf"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-zsh_arm64_2023-04-26_12-24-rootfs.tar.zst
# SHA256SUM=8d8af37ef011c975a4b099481ba5c82d8a0a467865f1b83b012bd369438f83af
# BUILD_DATE=20230426
# BUILD_TAG=2023-04-26
# STATUS=completed
# VERSION=latest02
# END_TIME=12:24

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-26
begin = 2023-04-26 12:02:41.644263041+00:00
start-sync_0 = 12:18:14
start-zstd = 12:20:12
start-sync_1 = 12:23:44
end-sync_1 = 12:24:03
end = 2023-04-26 12:24:03.111710947+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-9) 2.36'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'
```
