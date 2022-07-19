# fedora-zsh-amd64

## How to run it?

```sh
docker run \
    -it \
    --name fedora-zsh-amd64 \
    cake233/fedora-zsh-amd64
```

## How to exec shell?

```sh
docker exec -it fedora-zsh-amd64 zsh
```

## fedora-zsh-amd64.toml

```toml
[main]
name = "fedora"
tag = ["zsh", "2022-07-19"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-zsh_amd64_2022-07-19_12-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c03f9f7d58ef2e4c3847e56f127ab80c5d8a69af3e250d71e5bdf1c9d2b486d7"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1098545664

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "182M"
zstd_bytes = 190814984

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220712"
previous_tag = "2022-07-12"
previous_file = "fedora-zsh_amd64_2022-07-12_12-09-rootfs.tar.zst"
previous_sha256 = "10d070f7a2335fa9eca151daba478c58fa860b10afe6210685b5e7696114f8a6"

current_version = "latest01"
current_date = "20220719"
old_file = "fedora-zsh_amd64_2022-07-05_12-09-rootfs.tar.zst"
old_sha256 = "45da92bef32c93d9acc7784b8456c56b0e81742f00a610385c7b373d3991fd00"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-zsh_amd64_2022-07-19_12-09-rootfs.tar.zst
# SHA256SUM=c03f9f7d58ef2e4c3847e56f127ab80c5d8a69af3e250d71e5bdf1c9d2b486d7
# BUILD_DATE=20220719
# BUILD_TAG=2022-07-19
# STATUS=completed
# VERSION=latest01
# END_TIME=12:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-19
begin = 2022-07-19 12:02:27.256130030+00:00
start-sync_0 = 12:04:17
start-zstd = 12:06:10
start-sync_1 = 12:09:41
end-sync_1 = 12:09:57
end = 2022-07-19 12:09:57.472517905+00:00

[server]
repo = "cake233/fedora-zsh-amd64"

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
ldd = 'ldd (GNU libc) 2.35.9000'
zsh = 'zsh 5.9 (x86_64-redhat-linux-gnu)'
```
