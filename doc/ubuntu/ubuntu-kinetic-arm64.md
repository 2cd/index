# ubuntu-kinetic-arm64

## How to run it?

```sh
docker run \
    -it \
    --name ubuntu-kinetic-arm64 \
    cake233/ubuntu-kinetic-arm64
```

## How to exec shell?

```sh
docker exec -it ubuntu-kinetic-arm64 sh
```

## ubuntu-kinetic-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["kinetic", "2022-04-30", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-kinetic_arm64_2022-04-30_00-11.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a3d627f90ac956246f45e6b27903c706ec900c20058502819a5f594d137aef89"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "409M"
tar_bytes = 428809216

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "69M"
zstd_bytes = 71576914

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220429"
previous_tag = "2022-04-29"
previous_file = "ubuntu-kinetic_arm64_2022-04-29_00-10-rootfs.tar.zst"
previous_sha256 = "9e2c8e5fdbd00377f862b804248f26746b05d39871dc675e59fa3b9558f664a2"

current_version = "latest02"
current_date = "20220430"
old_file = "ubuntu-kinetic_arm64_2022-04-28_00-10-rootfs.tar.zst"
old_sha256 = "d5435727b70eeb2005c02058fc110de8d4b23d6d6a95ed13ae53f36e695f3849"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-kinetic_arm64_2022-04-30_00-11-rootfs.tar.zst
# SHA256SUM=a3d627f90ac956246f45e6b27903c706ec900c20058502819a5f594d137aef89
# BUILD_DATE=20220430
# BUILD_TAG=2022-04-30
# STATUS=completed
# VERSION=latest02
# END_TIME=00:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-30
begin = 2022-04-30 00:04:29.141624488+00:00
start-sync_0 = 00:09:34
start-zstd = 00:10:02
start-sync_1 = 00:11:34
end-sync_1 = 00:11:44
end = 2022-04-30 00:11:44.884469042+00:00

[server]
repo = "cake233/ubuntu-kinetic-arm64"

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
