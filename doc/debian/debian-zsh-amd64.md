# debian-zsh-amd64

## How to run it?

```sh
docker run \
    -it \
    --name debian-zsh-amd64 \
    cake233/debian-zsh-amd64
```

## How to exec shell?

```sh
docker exec -it debian-zsh-amd64 zsh
```

## debian-zsh-amd64.toml

```toml
[main]
name = "debian"
tag = ["zsh", "2023-08-30"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_amd64_2023-08-30_12-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f0d311bde7bd99c7550c277ad694bc67a0dfda24b0f06bc9906b9c982c4be91a"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "816M"
tar_bytes = 855401984

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "163M"
zstd_bytes = 170036858

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20230830"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-zsh_amd64_2023-08-30_12-10-rootfs.tar.zst
# SHA256SUM=f0d311bde7bd99c7550c277ad694bc67a0dfda24b0f06bc9906b9c982c4be91a
# BUILD_DATE=20230830
# BUILD_TAG=2023-08-30
# STATUS=completed
# VERSION=latest01
# END_TIME=12:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-30
begin = 2023-08-30 12:02:39.404139234+00:00
start-sync_0 = 12:05:17
start-zstd = 12:06:59
start-sync_1 = 12:09:47
end-sync_1 = 12:10:07
end = 2023-08-30 12:10:07.247909643+00:00

[server]
repo = "cake233/debian-zsh-amd64"

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
ldd = 'ldd (Debian GLIBC 2.37-7) 2.37'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'
```