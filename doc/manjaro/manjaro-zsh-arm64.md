# manjaro-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name manjaro-zsh-arm64 \
    cake233/manjaro-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it manjaro-zsh-arm64 zsh
```

## manjaro-zsh-arm64.toml

```toml
[main]
name = "manjaro"
tag = ["zsh", "2022-05-20"]
os = "manjaro"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-zsh_arm64_2022-05-20_12-18.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8330dcae3a7f8f034bc22b788cd199c6920fbaebc68e30a93b661833ce0949d6"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.2G"
tar_bytes = 1182040064

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "251M"
zstd_bytes = 262814682

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220513"
previous_tag = "2022-05-13"
previous_file = "manjaro-zsh_arm64_2022-05-13_12-15-rootfs.tar.zst"
previous_sha256 = "344a8aeeb059b5e545d71d9a8a147e4815f9d682e78317cd0dd7d2fb7de2ff9e"

current_version = "latest02"
current_date = "20220520"
old_file = "manjaro-zsh_arm64_2022-05-06_12-17-rootfs.tar.zst"
old_sha256 = "ff5ba39b58d84994453f28030896d4a49c7b15535e1ba88211197822a8fc048d"
# edition 2021
# DISTRO_NAME=manjaro-stable_arm64
# ROOTFS_FILE=manjaro-zsh_arm64_2022-05-20_12-18-rootfs.tar.zst
# SHA256SUM=8330dcae3a7f8f034bc22b788cd199c6920fbaebc68e30a93b661833ce0949d6
# BUILD_DATE=20220520
# BUILD_TAG=2022-05-20
# STATUS=completed
# VERSION=latest02
# END_TIME=12:18

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-20
begin = 2022-05-20 12:02:29.520773548+00:00
start-sync_0 = 12:10:57
start-zstd = 12:12:29
start-sync_1 = 12:18:21
end-sync_1 = 12:18:44
end = 2022-05-20 12:18:44.858887817+00:00

[server]
repo = "cake233/manjaro-zsh-arm64"

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
zsh = 'zsh 5.8.1 (aarch64-unknown-linux-gnu)'
```
