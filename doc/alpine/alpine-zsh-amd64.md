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
tag = ["zsh", "2023-02-16"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_amd64_2023-02-16_00-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "946b6a57134234fb5edd55f9b43c69211f9f5cef20b1e5f5d9190f5db245363b"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "96M"
tar_bytes = 100121088

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "31M"
zstd_bytes = 32441564

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230209"
previous_tag = "2023-02-09"
previous_file = "alpine-zsh_amd64_2023-02-09_00-05-rootfs.tar.zst"
previous_sha256 = "c777dac6957db2d3a9184717db5ecc5436b07935a3586a03160b7c1b2f8e10ec"

current_version = "latest02"
current_date = "20230216"
old_file = "alpine-zsh_amd64_2023-02-02_00-04-rootfs.tar.zst"
old_sha256 = "3b551ad69f15a7f5ad4755725b1f3c0cdc1bfaae95a567889c85f0666a837399"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-zsh_amd64_2023-02-16_00-05-rootfs.tar.zst
# SHA256SUM=946b6a57134234fb5edd55f9b43c69211f9f5cef20b1e5f5d9190f5db245363b
# BUILD_DATE=20230216
# BUILD_TAG=2023-02-16
# STATUS=completed
# VERSION=latest02
# END_TIME=00:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-16
begin = 2023-02-16 00:02:25.803578751+00:00
start-sync_0 = 00:03:10
start-zstd = 00:04:33
start-sync_1 = 00:05:04
end-sync_1 = 00:05:13
end = 2023-02-16 00:05:13.607173679+00:00

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
zsh = 'zsh 5.9 (x86_64-alpine-linux-musl)'
```
