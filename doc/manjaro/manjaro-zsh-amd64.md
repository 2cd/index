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
tag = ["zsh", "2022-05-27"]
os = "manjaro"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-zsh_amd64_2022-05-27_12-13.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "4ac1d5d0c5e2a2be1185e559a355ff870b9e93a4f91618abb45b1ba8ea096497"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1180058112

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "269M"
zstd_bytes = 281517474

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220520"
previous_tag = "2022-05-20"
previous_file = "manjaro-zsh_amd64_2022-05-20_12-11-rootfs.tar.zst"
previous_sha256 = "9722240e257a44b2bc8245a3ec4915a4573f02a87955452faae6313c00ec5414"

current_version = "latest01"
current_date = "20220527"
old_file = "manjaro-zsh_amd64_2022-05-13_12-12-rootfs.tar.zst"
old_sha256 = "32f0dadf268d31e0395c5276f602792da82c0463d2848200daf7c3ccae1a90ce"
# edition 2021
# DISTRO_NAME=manjaro-stable_amd64
# ROOTFS_FILE=manjaro-zsh_amd64_2022-05-27_12-13-rootfs.tar.zst
# SHA256SUM=4ac1d5d0c5e2a2be1185e559a355ff870b9e93a4f91618abb45b1ba8ea096497
# BUILD_DATE=20220527
# BUILD_TAG=2022-05-27
# STATUS=completed
# VERSION=latest01
# END_TIME=12:13

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-27
begin = 2022-05-27 12:02:39.613021332+00:00
start-sync_0 = 12:05:03
start-zstd = 12:06:53
start-sync_1 = 12:12:37
end-sync_1 = 12:13:01
end = 2022-05-27 12:13:01.651037617+00:00

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
