# debian-zsh-armv7

## How to run it?

```sh
docker run \
    -it \
    --name debian-zsh-armv7 \
    cake233/debian-zsh-armv7
```

## How to exec shell?

```sh
docker exec -it debian-zsh-armv7 zsh
```

## debian-zsh-armv7.toml

```toml
[main]
name = "debian"
tag = ["zsh", "2022-12-21"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_armhf_2022-12-21_12-17.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "e403984a131ee37ac2535726307d433b76529d66f60b91ae5fb8088312c08f87"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "735M"
tar_bytes = 770051072

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "141M"
zstd_bytes = 147326208

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221214"
previous_tag = "2022-12-14"
previous_file = "debian-zsh_armhf_2022-12-14_12-17-rootfs.tar.zst"
previous_sha256 = "11856585c64ce951ab46a4eb1de5a4524a99e16132983209189fcf6b7689507d"

current_version = "latest02"
current_date = "20221221"
old_file = "debian-zsh_armhf_2022-12-07_12-17-rootfs.tar.zst"
old_sha256 = "8b74c2dee2e019303433dfcd43b475d941f7d0451c4061192af70a4fde55805c"
# edition 2021
# DISTRO_NAME=debian-sid_armhf
# ROOTFS_FILE=debian-zsh_armhf_2022-12-21_12-17-rootfs.tar.zst
# SHA256SUM=e403984a131ee37ac2535726307d433b76529d66f60b91ae5fb8088312c08f87
# BUILD_DATE=20221221
# BUILD_TAG=2022-12-21
# STATUS=completed
# VERSION=latest02
# END_TIME=12:17

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-21
begin = 2022-12-21 12:02:26.489989850+00:00
start-sync_0 = 12:13:00
start-zstd = 12:14:46
start-sync_1 = 12:16:49
end-sync_1 = 12:17:03
end = 2022-12-21 12:17:03.597817879+00:00

[server]
repo = "cake233/debian-zsh-armv7"

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
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabihf)'
```
