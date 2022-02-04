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
tag = ["zsh", "2022-02-04"]
os = "manjaro"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "manjaro-zsh_amd64_2022-02-04_12-12.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "511d64fd633e38fee1080baffe7a973824470b4b09ea2c33fdf99676fea24ba2"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1175539200

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "257M"
zstd_bytes = 268977506

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220128"
previous_tag = "2022-01-28"
previous_file = "manjaro-zsh_amd64_2022-01-28_12-12-rootfs.tar.zst"
previous_sha256 = "4a3afc51bc5c82d2b34a10bee1c63be425b807026de4ba5b9afdf588040c6a71"

current_version = "latest01"
current_date = "20220204"
old_file = "manjaro-zsh_amd64_2022-01-21_12-12-rootfs.tar.zst"
old_sha256 = "ae755163d36e5773352be2fe663cdb104267c49938133b5ff198b7001cef088d"
# edition 2021
# DISTRO_NAME=manjaro-stable_amd64
# ROOTFS_FILE=manjaro-zsh_amd64_2022-02-04_12-12-rootfs.tar.zst
# SHA256SUM=511d64fd633e38fee1080baffe7a973824470b4b09ea2c33fdf99676fea24ba2
# BUILD_DATE=20220204
# BUILD_TAG=2022-02-04
# STATUS=completed
# VERSION=latest01
# END_TIME=12:12

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-04
begin = 2022-02-04 12:02:28.569870459+00:00
start-sync_0 = 12:06:11
start-zstd = 12:07:46
start-sync_1 = 12:12:17
end-sync_1 = 12:12:42
end = 2022-02-04 12:12:42.983225311+00:00

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
