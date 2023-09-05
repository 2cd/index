# euler-amd64

## How to run it?

```sh
docker run \
    -it \
    --name euler-amd64 \
    cake233/euler-amd64
```

## How to exec shell?

```sh
docker exec -it euler-amd64 sh
```

## euler-amd64.toml

```toml
[main]
name = "euler"
tag = ["base", "2023-03-15"]
os = "euler"
release = "base"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "euler_amd64_2023-03-15_00-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "43cf404aa6acb2e23ff230d4f30409bb41a936caff51a8a14569ae2a35d148c9"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "443M"
tar_bytes = 463643648

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "70M"
zstd_bytes = 72694426

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230215"
previous_tag = "2023-02-15"
previous_file = "euler_amd64_2023-02-15_00-06-rootfs.tar.zst"
previous_sha256 = "f7663d7e6bbe24f4b98d0fdefe119eb64df458b1e8fe1eaa22fad8e1656f2357"

current_version = "latest01"
current_date = "20230315"
old_file = "euler_amd64_2023-01-15_00-07-rootfs.tar.zst"
old_sha256 = "3a34bdb46194c01fbc87e7e8506dfd25054804f6ee38264691349a35da86cca9"
# edition 2021
# DISTRO_NAME=euler_amd64
# ROOTFS_FILE=euler_amd64_2023-03-15_00-06-rootfs.tar.zst
# SHA256SUM=43cf404aa6acb2e23ff230d4f30409bb41a936caff51a8a14569ae2a35d148c9
# BUILD_DATE=20230315
# BUILD_TAG=2023-03-15
# STATUS=completed
# VERSION=latest01
# END_TIME=00:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-15
begin = 2023-03-15 00:03:17.534456019+00:00
start-sync_0 = 00:04:32
start-zstd = 00:05:00
start-sync_1 = 00:06:34
end-sync_1 = 00:06:47
end = 2023-03-15 00:06:47.556359284+00:00

[server]
repo = "cake233/euler-amd64"

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