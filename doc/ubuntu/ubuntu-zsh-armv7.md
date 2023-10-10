# ubuntu-zsh-armv7

## How to run it?

```sh
docker run \
    -it \
    --name ubuntu-zsh-armv7 \
    cake233/ubuntu-zsh-armv7
```

## How to exec shell?

```sh
docker exec -it ubuntu-zsh-armv7 zsh
```

## ubuntu-zsh-armv7.toml

```toml
[main]
name = "ubuntu"
tag = ["zsh", "2023-10-10", "devel"]
os = "ubuntu"
release = "dev"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-zsh_armhf_2023-10-10_00-20.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "022f5505223a40d8a1a6b13e858c602bf374d803684be075bf2baec6218265a2"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "707M"
tar_bytes = 740617728

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "149M"
zstd_bytes = 155407856

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231003"
previous_tag = "2023-10-03"
previous_file = "ubuntu-zsh_armhf_2023-10-03_00-20-rootfs.tar.zst"
previous_sha256 = "784dc080590496bb0306614d33cfee10cd8f102085ad9f22c79911697ab9f9ee"

current_version = "latest02"
current_date = "20231010"
old_file = "ubuntu-zsh_armhf_2023-09-26_00-21-rootfs.tar.zst"
old_sha256 = "23cc1274a3f56948dc8c21279beacd57f6c43b39a30719b214f0adb9eb61532d"
# edition 2021
# DISTRO_NAME=ubuntu-dev_armhf
# ROOTFS_FILE=ubuntu-zsh_armhf_2023-10-10_00-20-rootfs.tar.zst
# SHA256SUM=022f5505223a40d8a1a6b13e858c602bf374d803684be075bf2baec6218265a2
# BUILD_DATE=20231010
# BUILD_TAG=2023-10-10
# STATUS=completed
# VERSION=latest02
# END_TIME=00:20

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-10
begin = 2023-10-10 00:02:36.035947058+00:00
start-sync_0 = 00:16:41
start-zstd = 00:18:20
start-sync_1 = 00:20:29
end-sync_1 = 00:20:44
end = 2023-10-10 00:20:44.199483238+00:00

[server]
repo = "cake233/ubuntu-zsh-armv7"

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
ldd = 'ldd (Ubuntu GLIBC 2.38-1ubuntu6) 2.38'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabihf)'
```
