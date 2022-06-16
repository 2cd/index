# alpine-zsh-amd64

## How to run it?

```sh
docker run \
    -it \
    --name alpine-zsh-amd64 \
    cake233/alpine-zsh-amd64
```

## How to exec shell?

```sh
docker exec -it alpine-zsh-amd64 zsh
```

## alpine-zsh-amd64.toml

```toml
[main]
name = "alpine"
tag = ["zsh", "2022-06-16"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_amd64_2022-06-16_00-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "db5416077691d3993767b6935c7b978a2a52f137198b39e076739d7365af00c3"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "95M"
tar_bytes = 98602496

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "28M"
zstd_bytes = 28991670

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220609"
previous_tag = "2022-06-09"
previous_file = "alpine-zsh_amd64_2022-06-09_00-05-rootfs.tar.zst"
previous_sha256 = "66bcb121937a5bc13ce85279cff36309b8bf67b8ad301f13ff63c6d1f64999af"

current_version = "latest01"
current_date = "20220616"
old_file = "alpine-zsh_amd64_2022-06-02_00-04-rootfs.tar.zst"
old_sha256 = "8a387fc96dfaaaf190c624a06fa7a14f36b773315e6d955a2ac6ad4bcc9365b7"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-zsh_amd64_2022-06-16_00-04-rootfs.tar.zst
# SHA256SUM=db5416077691d3993767b6935c7b978a2a52f137198b39e076739d7365af00c3
# BUILD_DATE=20220616
# BUILD_TAG=2022-06-16
# STATUS=completed
# VERSION=latest01
# END_TIME=00:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-16
begin = 2022-06-16 00:02:27.903029363+00:00
start-sync_0 = 00:02:55
start-zstd = 00:04:16
start-sync_1 = 00:04:47
end-sync_1 = 00:04:53
end = 2022-06-16 00:04:53.526729291+00:00

[server]
repo = "cake233/alpine-zsh-amd64"

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
LANG = "C.UTF-8"

[version]
ldd = 'musl libc (x86_64) Version 1.2.3'
zsh = 'zsh 5.8.1 (x86_64-alpine-linux-musl)'
```
