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
tag = ["zsh", "2022-01-27"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "alpine-zsh_amd64_2022-01-27_00-05.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "91da038cc6387130e6b56d46c145b375f4ae0a5a5393849542b00b32d62cd635"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "93M"
tar_bytes = 96812544

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "27M"
zstd_bytes = 27849840

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220120"
previous_tag = "2022-01-20"
previous_file = "alpine-zsh_amd64_2022-01-20_00-05-rootfs.tar.zst"
previous_sha256 = "8c454f94adab04b1958a2b6ee1aefde833884775b69342d9477b47aea32dc871"

current_version = "latest02"
current_date = "20220127"
old_file = "alpine-zsh_amd64_2022-01-13_00-05-rootfs.tar.zst"
old_sha256 = "838b15524c60cc6f169c759974f3be9d7164e41a407685cb74da1a97d7c89d74"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-zsh_amd64_2022-01-27_00-05-rootfs.tar.zst
# SHA256SUM=91da038cc6387130e6b56d46c145b375f4ae0a5a5393849542b00b32d62cd635
# BUILD_DATE=20220127
# BUILD_TAG=2022-01-27
# STATUS=completed
# VERSION=latest02
# END_TIME=00:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-27
begin = 2022-01-27 00:02:23.190586001+00:00
start-sync_0 = 00:02:54
start-zstd = 00:04:17
start-sync_1 = 00:04:53
end-sync_1 = 00:05:02
end = 2022-01-27 00:05:02.193655625+00:00

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
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
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
ldd = 'musl libc (x86_64) Version 1.2.2'
zsh = 'zsh 5.8 (x86_64-alpine-linux-musl)'
```
