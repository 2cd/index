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
tag = ["zsh", "2023-04-12"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-zsh_armhf_2023-04-12_00-28.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "825890d452461b8c0fa3a3745503dd357a761c70a2f265cafc2d98bbd4f82006"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "912M"
tar_bytes = 956022272

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "223M"
zstd_bytes = 233824019

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230405"
previous_tag = "2023-04-05"
previous_file = "arch-zsh_armhf_2023-04-05_00-28-rootfs.tar.zst"
previous_sha256 = "760c2e8d3be91d25cba553e54906ec32601d3126edba1f885aa4efac3c9f53e8"

current_version = "latest02"
current_date = "20230412"
old_file = "arch-zsh_armhf_2023-03-29_00-33-rootfs.tar.zst"
old_sha256 = "2ce3f3b075e0e47ef0b4e5d9d8b76e8502601352d2a16db7ac3db75f15781eed"
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch-zsh_armhf_2023-04-12_00-28-rootfs.tar.zst
# SHA256SUM=825890d452461b8c0fa3a3745503dd357a761c70a2f265cafc2d98bbd4f82006
# BUILD_DATE=20230412
# BUILD_TAG=2023-04-12
# STATUS=completed
# VERSION=latest02
# END_TIME=00:28

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-12
begin = 2023-04-12 00:03:00.794826352+00:00
start-sync_0 = 00:23:00
start-zstd = 00:24:38
start-sync_1 = 00:28:21
end-sync_1 = 00:28:38
end = 2023-04-12 00:28:38.856908292+00:00

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
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.9 (armv7l-unknown-linux-gnueabihf)'
```
