# manjaro-zsh-amd64

## How to run it?

```sh
docker run \
    -it \
    --name manjaro-zsh-amd64 \
    cake233/manjaro-zsh-amd64
```

## How to exec shell?

```sh
docker exec -it manjaro-zsh-amd64 zsh
```

## manjaro-zsh-amd64.toml

```toml
[main]
name = "manjaro"
tag = ["zsh", "2022-01-28"]
os = "manjaro"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "manjaro-zsh_amd64_2022-01-28_12-12.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "4a3afc51bc5c82d2b34a10bee1c63be425b807026de4ba5b9afdf588040c6a71"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1175519232

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "257M"
zstd_bytes = 268942381

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220121"
previous_tag = "2022-01-21"
previous_file = "manjaro-zsh_amd64_2022-01-21_12-12-rootfs.tar.zst"
previous_sha256 = "ae755163d36e5773352be2fe663cdb104267c49938133b5ff198b7001cef088d"

current_version = "latest02"
current_date = "20220128"
old_file = "manjaro-zsh_amd64_2022-01-14_12-11-rootfs.tar.zst"
old_sha256 = "afbc624353fa703f03a7ced6f3d06dce2bf725b3095c8d05be91418ec55c0a6e"
# edition 2021
# DISTRO_NAME=manjaro-stable_amd64
# ROOTFS_FILE=manjaro-zsh_amd64_2022-01-28_12-12-rootfs.tar.zst
# SHA256SUM=4a3afc51bc5c82d2b34a10bee1c63be425b807026de4ba5b9afdf588040c6a71
# BUILD_DATE=20220128
# BUILD_TAG=2022-01-28
# STATUS=completed
# VERSION=latest02
# END_TIME=12:12

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-28
begin = 2022-01-28 12:02:25.494583061+00:00
start-sync_0 = 12:04:52
start-zstd = 12:06:32
start-sync_1 = 12:11:37
end-sync_1 = 12:12:03
end = 2022-01-28 12:12:03.788637024+00:00

[server]
repo = "cake233/manjaro-zsh-amd64"

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
ldd = 'ldd (GNU libc) 2.33'
zsh = 'zsh 5.8 (x86_64-pc-linux-gnu)'
```
