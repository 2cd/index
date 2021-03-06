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
tag = ["zsh", "2022-07-20"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-zsh_amd64_2022-07-20_00-20.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "12064486481b7e5682c9be9e8b8970bfb008c8d6dbf99f329bbf34149b0fbcc0"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "975M"
tar_bytes = 1021661696

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "246M"
zstd_bytes = 257696564

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220713"
previous_tag = "2022-07-13"
previous_file = "arch-zsh_amd64_2022-07-13_00-19-rootfs.tar.zst"
previous_sha256 = "57fc20d00907d149a79db4551bba17b6b4ddf8438dc8a62ac5b21172a767d302"

current_version = "latest01"
current_date = "20220720"
old_file = "arch-zsh_amd64_2022-07-06_00-16-rootfs.tar.zst"
old_sha256 = "da3e057a7eff510f2eb8709e9048316c6db3f3edabd6cf721c5c979fb0edd1a6"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-zsh_amd64_2022-07-20_00-20-rootfs.tar.zst
# SHA256SUM=12064486481b7e5682c9be9e8b8970bfb008c8d6dbf99f329bbf34149b0fbcc0
# BUILD_DATE=20220720
# BUILD_TAG=2022-07-20
# STATUS=completed
# VERSION=latest01
# END_TIME=00:20

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-20
begin = 2022-07-20 00:12:38.605240723+00:00
start-sync_0 = 00:15:05
start-zstd = 00:16:42
start-sync_1 = 00:20:08
end-sync_1 = 00:20:33
end = 2022-07-20 00:20:33.625745708+00:00

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
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'
```
