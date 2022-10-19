# arch-zsh-amd64

## How to run it?

```sh
docker run \
    -it \
    --name arch-zsh-amd64 \
    cake233/arch-zsh-amd64
```

## How to exec shell?

```sh
docker exec -it arch-zsh-amd64 zsh
```

## arch-zsh-amd64.toml

```toml
[main]
name = "arch"
tag = ["zsh", "2022-10-19"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-zsh_amd64_2022-10-19_00-15.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f6189a0abdd632f003e05beaf1430b030c2f1e7d126be09af7c7862250201e6c"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1023M"
tar_bytes = 1072126976

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "258M"
zstd_bytes = 269786452

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221012"
previous_tag = "2022-10-12"
previous_file = "arch-zsh_amd64_2022-10-12_00-15-rootfs.tar.zst"
previous_sha256 = "d231fc0d85267b44f4e28413b619764864a6efcf497ed603d3f9d5db91d07cb6"

current_version = "latest01"
current_date = "20221019"
old_file = "arch-zsh_amd64_2022-10-05_00-19-rootfs.tar.zst"
old_sha256 = "00f9b908893bfac4cb6b7d02474e4a831ab202077078c848379d596e741492a5"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-zsh_amd64_2022-10-19_00-15-rootfs.tar.zst
# SHA256SUM=f6189a0abdd632f003e05beaf1430b030c2f1e7d126be09af7c7862250201e6c
# BUILD_DATE=20221019
# BUILD_TAG=2022-10-19
# STATUS=completed
# VERSION=latest01
# END_TIME=00:15

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-19
begin = 2022-10-19 00:07:35.641504980+00:00
start-sync_0 = 00:10:09
start-zstd = 00:11:37
start-sync_1 = 00:15:21
end-sync_1 = 00:15:41
end = 2022-10-19 00:15:41.712558299+00:00

[server]
repo = "cake233/arch-zsh-amd64"

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
ldd = 'ldd (GNU libc) 2.36'
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'
```
