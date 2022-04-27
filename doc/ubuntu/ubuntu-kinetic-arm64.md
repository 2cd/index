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
tag = ["kinetic", "2022-04-27", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-kinetic_arm64_2022-04-27_00-14.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8ee9b50ac20616aed8a7846ba27cd27a0cd6cf3a024786d6826ed24a6bda8c15"

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
zstd_bytes = 71489568

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220426"
previous_tag = "2022-04-26"
previous_file = "ubuntu-kinetic_arm64_2022-04-26_00-10-rootfs.tar.zst"
previous_sha256 = "87769804d680bb42ecba8a2b366f380ab73df05c1fe790e590366436e67b39fe"

current_version = "latest01"
current_date = "20220427"
old_file = "ubuntu-kinetic_arm64_2022-04-25_19-31-rootfs.tar.zst"
old_sha256 = "6171e27d793dd9b53d76a7ccac0f42a5b0089ddb4d3f61ff46ce15d4c2d3c2eb"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-kinetic_arm64_2022-04-27_00-14-rootfs.tar.zst
# SHA256SUM=8ee9b50ac20616aed8a7846ba27cd27a0cd6cf3a024786d6826ed24a6bda8c15
# BUILD_DATE=20220427
# BUILD_TAG=2022-04-27
# STATUS=completed
# VERSION=latest01
# END_TIME=00:14

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-27
begin = 2022-04-27 00:07:52.787482870+00:00
start-sync_0 = 00:12:31
start-zstd = 00:13:03
start-sync_1 = 00:14:30
end-sync_1 = 00:14:42
end = 2022-04-27 00:14:42.786586139+00:00

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
