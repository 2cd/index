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
tag = ["zsh", "2022-04-05"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "arch-zsh_armhf_2022-04-05_23-30.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "6d4444fd7abb56afca00dddafdb7757ac259f0ecec065ba66d414d4642525422"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "855M"
tar_bytes = 896139776

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "209M"
zstd_bytes = 219028496

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220329"
previous_tag = "2022-03-29"
previous_file = "arch-zsh_armhf_2022-03-29_23-32-rootfs.tar.zst"
previous_sha256 = "f2e1daf85e332d54601a42ec0b88e5f6622e22f4c3da36865fe195b9d609d725"

current_version = "latest01"
current_date = "20220405"
old_file = "arch-zsh_armhf_2022-03-23_00-33-rootfs.tar.zst"
old_sha256 = "64fd3a537c6d3433e5a9a04f280b7350087be73ba75c2dcfe1e74ba39cccacd8"
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch-zsh_armhf_2022-04-05_23-30-rootfs.tar.zst
# SHA256SUM=6d4444fd7abb56afca00dddafdb7757ac259f0ecec065ba66d414d4642525422
# BUILD_DATE=20220405
# BUILD_TAG=2022-04-05
# STATUS=completed
# VERSION=latest01
# END_TIME=23:30

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-05
begin = 2022-04-05 23:05:53.315139105+00:00
start-sync_0 = 23:24:08
start-zstd = 23:25:49
start-sync_1 = 23:29:42
end-sync_1 = 23:30:02
end = 2022-04-05 23:30:02.832094520+00:00

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
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.8.1 (armv7l-unknown-linux-gnueabihf)'
```
