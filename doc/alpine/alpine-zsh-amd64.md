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
tag = ["zsh", "2022-12-22"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_amd64_2022-12-22_00-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "76d9e711f5b523f2688d74b982d9da245bcced039799a5780f492b7b27bf0479"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "92M"
tar_bytes = 96262656

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "29M"
zstd_bytes = 30008180

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221215"
previous_tag = "2022-12-15"
previous_file = "alpine-zsh_amd64_2022-12-15_00-05-rootfs.tar.zst"
previous_sha256 = "fd419d1dabfc329d022b71c375ae384a05f1475d213e6dd4d54626f42a44c617"

current_version = "latest02"
current_date = "20221222"
old_file = "alpine-zsh_amd64_2022-12-08_00-05-rootfs.tar.zst"
old_sha256 = "10ce40e49a50247ec9fc1c6370a6e11b9dbb75a54232ca15e68b937937e6f321"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-zsh_amd64_2022-12-22_00-05-rootfs.tar.zst
# SHA256SUM=76d9e711f5b523f2688d74b982d9da245bcced039799a5780f492b7b27bf0479
# BUILD_DATE=20221222
# BUILD_TAG=2022-12-22
# STATUS=completed
# VERSION=latest02
# END_TIME=00:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-22
begin = 2022-12-22 00:02:24.321011070+00:00
start-sync_0 = 00:02:59
start-zstd = 00:04:20
start-sync_1 = 00:04:56
end-sync_1 = 00:05:03
end = 2022-12-22 00:05:03.474631389+00:00

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
