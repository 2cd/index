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
tag = ["zsh", "2023-06-23"]
os = "manjaro"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-zsh_amd64_2023-06-23_12-11.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "500fb54ed0b6212794ad00e531f23f37b4de26fbf61763d1ea3331d9125c7265"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.2G"
tar_bytes = 1248196608

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "287M"
zstd_bytes = 300122602

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230616"
previous_tag = "2023-06-16"
previous_file = "manjaro-zsh_amd64_2023-06-16_12-13-rootfs.tar.zst"
previous_sha256 = "3616e019d2da6f450d644f4360be06999ca6dfaf112f9b834e9022b2c56673d8"

current_version = "latest01"
current_date = "20230623"
old_file = "manjaro-zsh_amd64_2023-06-09_12-12-rootfs.tar.zst"
old_sha256 = "979b7c01ffd9d42c40d5e0dce7afaad2596790eece8a683b906b34e608d98a64"
# edition 2021
# DISTRO_NAME=manjaro-stable_amd64
# ROOTFS_FILE=manjaro-zsh_amd64_2023-06-23_12-11-rootfs.tar.zst
# SHA256SUM=500fb54ed0b6212794ad00e531f23f37b4de26fbf61763d1ea3331d9125c7265
# BUILD_DATE=20230623
# BUILD_TAG=2023-06-23
# STATUS=completed
# VERSION=latest01
# END_TIME=12:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-23
begin = 2023-06-23 12:02:37.040314414+00:00
start-sync_0 = 12:04:55
start-zstd = 12:06:36
start-sync_1 = 12:11:37
end-sync_1 = 12:11:58
end = 2023-06-23 12:11:58.309567581+00:00

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
ldd = 'ldd (GNU libc) 2.37'
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'
```
