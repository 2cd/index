# alpine-zsh-386

## How to run it?

```sh
docker run \
    -it \
    --name alpine-zsh-386 \
    cake233/alpine-zsh-386
```

## How to exec shell?

```sh
docker exec -it alpine-zsh-386 zsh
```

## alpine-zsh-386.toml

```toml
[main]
name = "alpine"
tag = ["zsh", "2023-06-08"]
os = "alpine"
release = "edge"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_i386_2023-06-08_00-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "216c9f82eed7c6de7e984a374cf5b86874618e2ed061b2df5ae011873888a140"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "92M"
tar_bytes = 96387072

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "31M"
zstd_bytes = 32117817

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230601"
previous_tag = "2023-06-01"
previous_file = "alpine-zsh_i386_2023-06-01_00-06-rootfs.tar.zst"
previous_sha256 = "9e86b695e0409d81eef16d6dfb21608e961071440360a7922d1aa35b30d2d494"

current_version = "latest01"
current_date = "20230608"
old_file = "alpine-zsh_i386_2023-05-25_00-06-rootfs.tar.zst"
old_sha256 = "57a4816e41a5ed334c5dde8fa583834ab9be8ba119632f8c8c52e85a780dbbc8"
# edition 2021
# DISTRO_NAME=alpine-edge_i386
# ROOTFS_FILE=alpine-zsh_i386_2023-06-08_00-05-rootfs.tar.zst
# SHA256SUM=216c9f82eed7c6de7e984a374cf5b86874618e2ed061b2df5ae011873888a140
# BUILD_DATE=20230608
# BUILD_TAG=2023-06-08
# STATUS=completed
# VERSION=latest01
# END_TIME=00:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-08
begin = 2023-06-08 00:02:30.586360245+00:00
start-sync_0 = 00:04:01
start-zstd = 00:05:22
start-sync_1 = 00:05:52
end-sync_1 = 00:05:59
end = 2023-06-08 00:05:59.333564049+00:00

[server]
repo = "cake233/alpine-zsh-386"

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
ldd = 'musl libc (i386) Version 1.2.4'
zsh = 'zsh 5.9 (i586-alpine-linux-musl)'
```
