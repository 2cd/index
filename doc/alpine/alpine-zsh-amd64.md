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
tag = ["zsh", "2022-11-03"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_amd64_2022-11-03_00-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "636e96fc54c28346630c5ce7ea8d03d4f47c0c9b7478c209dcbc1cf05e4112a7"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "92M"
tar_bytes = 96217088

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "29M"
zstd_bytes = 29997442

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221027"
previous_tag = "2022-10-27"
previous_file = "alpine-zsh_amd64_2022-10-27_00-05-rootfs.tar.zst"
previous_sha256 = "bef7a6fbe195998b089f24323246f80e89ee01fffad72b2c1903146370d752ac"

current_version = "latest02"
current_date = "20221103"
old_file = "alpine-zsh_amd64_2022-10-20_00-04-rootfs.tar.zst"
old_sha256 = "f93c1a27d1c5c6f7f597d48b23f6944fcc5f5cf5002603b678d52745ff3d94fe"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-zsh_amd64_2022-11-03_00-04-rootfs.tar.zst
# SHA256SUM=636e96fc54c28346630c5ce7ea8d03d4f47c0c9b7478c209dcbc1cf05e4112a7
# BUILD_DATE=20221103
# BUILD_TAG=2022-11-03
# STATUS=completed
# VERSION=latest02
# END_TIME=00:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-03
begin = 2022-11-03 00:02:21.274312713+00:00
start-sync_0 = 00:02:52
start-zstd = 00:04:13
start-sync_1 = 00:04:49
end-sync_1 = 00:04:55
end = 2022-11-03 00:04:55.272329141+00:00

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
