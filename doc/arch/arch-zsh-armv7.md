# arch-zsh-armv7

## How to run it?

```sh
docker run \
    -it \
    --name arch-zsh-armv7 \
    cake233/arch-zsh-armv7
```

## How to exec shell?

```sh
docker exec -it arch-zsh-armv7 zsh
```

## arch-zsh-armv7.toml

```toml
[main]
name = "arch"
tag = ["zsh", "2022-01-19"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "arch-zsh_armhf_2022-01-19_00-29.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "daef6df803554ae6796f936a6e44a64cff4966c8e26f06c9ef15f112f77b28eb"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "851M"
tar_bytes = 891702784

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "207M"
zstd_bytes = 216592943

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20220119"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch-zsh_armhf_2022-01-19_00-29-rootfs.tar.zst
# SHA256SUM=daef6df803554ae6796f936a6e44a64cff4966c8e26f06c9ef15f112f77b28eb
# BUILD_DATE=20220119
# BUILD_TAG=2022-01-19
# STATUS=completed
# VERSION=latest01
# END_TIME=00:29

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-19
begin = 2022-01-19 00:06:13.920408590+00:00
start-sync_0 = 00:24:16
start-zstd = 00:25:56
start-sync_1 = 00:29:28
end-sync_1 = 00:29:54
end = 2022-01-19 00:29:54.505868859+00:00

[server]
repo = "cake233/arch-zsh-armv7"

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
ldd = 'ldd (GNU libc) 2.32'
zsh = 'zsh 5.8 (armv7l-unknown-linux-gnueabihf)'
```
