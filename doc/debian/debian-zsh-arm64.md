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
tag = ["zsh", "2022-06-22"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_arm64_2022-06-22_12-22.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "64a95668fc8fff8b934176245d4c0efa8bc681188985b26f4b452f16c144c34e"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "750M"
tar_bytes = 786297856

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "147M"
zstd_bytes = 153507998

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220615"
previous_tag = "2022-06-15"
previous_file = "debian-zsh_arm64_2022-06-15_12-18-rootfs.tar.zst"
previous_sha256 = "4ae38b95a2bdcacb7870b5232d59018ca467750746a4db1f1c5748a84fb89efb"

current_version = "latest01"
current_date = "20220622"
old_file = "debian-zsh_arm64_2022-06-08_12-20-rootfs.tar.zst"
old_sha256 = "2c0d8a0d2717a4da1acc28e9d76f4a8527d9c234b100db1384ef39739d6182cb"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-zsh_arm64_2022-06-22_12-22-rootfs.tar.zst
# SHA256SUM=64a95668fc8fff8b934176245d4c0efa8bc681188985b26f4b452f16c144c34e
# BUILD_DATE=20220622
# BUILD_TAG=2022-06-22
# STATUS=completed
# VERSION=latest01
# END_TIME=12:22

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-22
begin = 2022-06-22 12:02:29.008362406+00:00
start-sync_0 = 12:17:29
start-zstd = 12:19:23
start-sync_1 = 12:22:02
end-sync_1 = 12:22:20
end = 2022-06-22 12:22:20.565220359+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-7) 2.33'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'
```
