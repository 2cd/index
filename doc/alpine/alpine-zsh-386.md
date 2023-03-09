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
tag = ["zsh", "2023-03-09"]
os = "alpine"
release = "edge"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_i386_2023-03-09_00-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "9f29f69ea28c78e85ccb61f106baba61c60ea4364254b193db63f7e83e15f4fb"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "96M"
tar_bytes = 100264960

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "32M"
zstd_bytes = 33297861

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230302"
previous_tag = "2023-03-02"
previous_file = "alpine-zsh_i386_2023-03-02_00-06-rootfs.tar.zst"
previous_sha256 = "f8c42f4cbcce646b1538e122740c87ce73352f5b90989275da0f60e42c288a2f"

current_version = "latest02"
current_date = "20230309"
old_file = "alpine-zsh_i386_2023-02-23_00-06-rootfs.tar.zst"
old_sha256 = "e8ba04b08ce9f5b7277f2bf924da5ea87161b1ecd043fcdecf1642ba1f27bfa1"
# edition 2021
# DISTRO_NAME=alpine-edge_i386
# ROOTFS_FILE=alpine-zsh_i386_2023-03-09_00-06-rootfs.tar.zst
# SHA256SUM=9f29f69ea28c78e85ccb61f106baba61c60ea4364254b193db63f7e83e15f4fb
# BUILD_DATE=20230309
# BUILD_TAG=2023-03-09
# STATUS=completed
# VERSION=latest02
# END_TIME=00:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-09
begin = 2023-03-09 00:02:26.559555015+00:00
start-sync_0 = 00:04:03
start-zstd = 00:05:26
start-sync_1 = 00:05:58
end-sync_1 = 00:06:06
end = 2023-03-09 00:06:06.704120371+00:00

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
ldd = 'musl libc (i386) Version 1.2.3'
zsh = 'zsh 5.9 (i586-alpine-linux-musl)'
```
