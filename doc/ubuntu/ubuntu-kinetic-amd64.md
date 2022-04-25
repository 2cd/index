# ubuntu-kinetic-amd64

## How to run it?

```sh
docker run \
    -it \
    --name ubuntu-kinetic-amd64 \
    cake233/ubuntu-kinetic-amd64
```

## How to exec shell?

```sh
docker exec -it ubuntu-kinetic-amd64 sh
```

## ubuntu-kinetic-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["kinetic", "2022-04-25", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-kinetic_amd64_2022-04-25_20-54.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a51f165a3c453823af5f52550406e45cca19e1a1f3c6ab5d60969e13ceb9a0a7"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "418M"
tar_bytes = 438179840

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "70M"
zstd_bytes = 73110017

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220425"
previous_tag = "2022-04-25"
previous_file = "ubuntu-kinetic_amd64_2022-04-25_19-26-rootfs.tar.zst"
previous_sha256 = "f4c020115ca9e0a6ac7332e74cd7b5e9dff783d972d6405f3a617c163ef84701"

current_version = "latest02"
current_date = "20220425"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-kinetic_amd64_2022-04-25_20-54-rootfs.tar.zst
# SHA256SUM=a51f165a3c453823af5f52550406e45cca19e1a1f3c6ab5d60969e13ceb9a0a7
# BUILD_DATE=20220425
# BUILD_TAG=2022-04-25
# STATUS=completed
# VERSION=latest02
# END_TIME=20:54

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-25
begin = 2022-04-25 20:51:05.327489826+00:00
start-sync_0 = 20:51:59
start-zstd = 20:52:33
start-sync_1 = 20:54:06
end-sync_1 = 20:54:20
end = 2022-04-25 20:54:20.811023707+00:00

[server]
repo = "cake233/ubuntu-kinetic-amd64"

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
```
