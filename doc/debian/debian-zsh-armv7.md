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
tag = ["zsh", "2022-07-27"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_armhf_2022-07-27_12-20.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "9b5d6ffa3e6cb000cc45848048ceeaf8ec2117f83df3226a7f9a0f9a8f276923"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "707M"
tar_bytes = 740803072

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "141M"
zstd_bytes = 147357890

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220713"
previous_tag = "2022-07-13"
previous_file = "debian-zsh_armhf_2022-07-13_12-17-rootfs.tar.zst"
previous_sha256 = "0d7be736f47a4da45390dcb9c727713d8d40d22081b867e14f501907c8ed9907"

current_version = "latest01"
current_date = "20220727"
old_file = "debian-zsh_armhf_2022-07-06_12-18-rootfs.tar.zst"
old_sha256 = "f14150e072ecc5a95f66a8a93bff74236e57d5af95fc391a04bfb2a7c87263ac"
# edition 2021
# DISTRO_NAME=debian-sid_armhf
# ROOTFS_FILE=debian-zsh_armhf_2022-07-27_12-20-rootfs.tar.zst
# SHA256SUM=9b5d6ffa3e6cb000cc45848048ceeaf8ec2117f83df3226a7f9a0f9a8f276923
# BUILD_DATE=20220727
# BUILD_TAG=2022-07-27
# STATUS=completed
# VERSION=latest01
# END_TIME=12:20

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-27
begin = 2022-07-27 12:02:33.000032961+00:00
start-sync_0 = 12:15:54
start-zstd = 12:17:46
start-sync_1 = 12:19:57
end-sync_1 = 12:20:16
end = 2022-07-27 12:20:16.773399342+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-8) 2.33'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabihf)'
```
