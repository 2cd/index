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
tag = ["zsh", "2022-01-07"]
os = "manjaro"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "manjaro-zsh_amd64_2022-01-07_12-11.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "cfd6f62ea6720f5d29cac7205a029ac22902f85dbea80e56b7a6f6b6bfa87384"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1175239168

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "258M"
zstd_bytes = 269989438

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211231"
previous_tag = "2021-12-31"
previous_file = "manjaro-zsh_amd64_2021-12-31_12-10-rootfs.tar.zst"
previous_sha256 = "ba1fdcb73ed37289f4b153d64773fd8d2c9819dfb649e19db615cac8778e9b33"

current_version = "latest01"
current_date = "20220107"
old_file = "manjaro-zsh_amd64_2021-12-24_12-10-rootfs.tar.zst"
old_sha256 = "c60677951e5aef884557221b2b056e16e50a397ee63f13dd640e57c7b0f84b56"
# edition 2021
# DISTRO_NAME=manjaro-stable_amd64
# ROOTFS_FILE=manjaro-zsh_amd64_2022-01-07_12-11-rootfs.tar.zst
# SHA256SUM=cfd6f62ea6720f5d29cac7205a029ac22902f85dbea80e56b7a6f6b6bfa87384
# BUILD_DATE=20220107
# BUILD_TAG=2022-01-07
# STATUS=completed
# VERSION=latest01
# END_TIME=12:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-07
begin = 2022-01-07 12:02:26.963650917+00:00
start-sync_0 = 12:04:36
start-zstd = 12:06:10
start-sync_1 = 12:11:21
end-sync_1 = 12:11:49
end = 2022-01-07 12:11:49.488274344+00:00

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
