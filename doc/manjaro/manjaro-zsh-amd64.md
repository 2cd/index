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
tag = ["zsh", "2022-11-25"]
os = "manjaro"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-zsh_amd64_2022-11-25_12-12.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "1d394a3c9d22475ef3e31cf0cc27bc74083bf7103edd433e3d38f165ea48ad99"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1174044160

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "275M"
zstd_bytes = 287507121

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221028"
previous_tag = "2022-10-28"
previous_file = "manjaro-zsh_amd64_2022-10-28_12-10-rootfs.tar.zst"
previous_sha256 = "c2b5e9d4a6676c76e7cdff82564411b9b456e96f8f249b1110598284d668a9bf"

current_version = "latest02"
current_date = "20221125"
old_file = "manjaro-zsh_amd64_2022-10-07_12-11-rootfs.tar.zst"
old_sha256 = "18dc676cfb98f43f57a6bd1e26db3184f4ed1e9ea016aa4ccdaaa4ea62ac1238"
# edition 2021
# DISTRO_NAME=manjaro-stable_amd64
# ROOTFS_FILE=manjaro-zsh_amd64_2022-11-25_12-12-rootfs.tar.zst
# SHA256SUM=1d394a3c9d22475ef3e31cf0cc27bc74083bf7103edd433e3d38f165ea48ad99
# BUILD_DATE=20221125
# BUILD_TAG=2022-11-25
# STATUS=completed
# VERSION=latest02
# END_TIME=12:12

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-25
begin = 2022-11-25 12:02:24.978493422+00:00
start-sync_0 = 12:05:18
start-zstd = 12:07:03
start-sync_1 = 12:11:39
end-sync_1 = 12:12:04
end = 2022-11-25 12:12:04.174380342+00:00

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
ldd = 'ldd (GNU libc) 2.36'
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'
```
