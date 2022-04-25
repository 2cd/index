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
tag = ["kinetic", "2022-04-25", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-kinetic_arm64_2022-04-25_20-56.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "4b9a708e5e367173a2cd303057ebdbb3cebd77d872215ac77e01534f7dee9956"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "408M"
tar_bytes = 427812352

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "69M"
zstd_bytes = 71481794

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220425"
previous_tag = "2022-04-25"
previous_file = "ubuntu-kinetic_arm64_2022-04-25_19-31-rootfs.tar.zst"
previous_sha256 = "6171e27d793dd9b53d76a7ccac0f42a5b0089ddb4d3f61ff46ce15d4c2d3c2eb"

current_version = "latest02"
current_date = "20220425"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-kinetic_arm64_2022-04-25_20-56-rootfs.tar.zst
# SHA256SUM=4b9a708e5e367173a2cd303057ebdbb3cebd77d872215ac77e01534f7dee9956
# BUILD_DATE=20220425
# BUILD_TAG=2022-04-25
# STATUS=completed
# VERSION=latest02
# END_TIME=20:56

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-25
begin = 2022-04-25 20:51:01.212450838+00:00
start-sync_0 = 20:54:50
start-zstd = 20:55:14
start-sync_1 = 20:56:29
end-sync_1 = 20:56:37
end = 2022-04-25 20:56:37.970417767+00:00

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
