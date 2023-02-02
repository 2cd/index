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
tag = ["zsh", "2023-02-02"]
os = "alpine"
release = "edge"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_i386_2023-02-02_00-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d2fe234e51828a9dfd1825d84762fe5c869745d414556522ba94ad9af2160d4d"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "94M"
tar_bytes = 97631744

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "30M"
zstd_bytes = 31366459

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230126"
previous_tag = "2023-01-26"
previous_file = "alpine-zsh_i386_2023-01-26_00-06-rootfs.tar.zst"
previous_sha256 = "3e1a6f2e178eb8410d38ed92a8a3cce44e0251fb6c33c0bb28b9702b33c8dab6"

current_version = "latest01"
current_date = "20230202"
old_file = "alpine-zsh_i386_2023-01-19_00-06-rootfs.tar.zst"
old_sha256 = "3f46277061f43a5e6fcb3f53c19357f10908521027076620d15378ad0581b150"
# edition 2021
# DISTRO_NAME=alpine-edge_i386
# ROOTFS_FILE=alpine-zsh_i386_2023-02-02_00-06-rootfs.tar.zst
# SHA256SUM=d2fe234e51828a9dfd1825d84762fe5c869745d414556522ba94ad9af2160d4d
# BUILD_DATE=20230202
# BUILD_TAG=2023-02-02
# STATUS=completed
# VERSION=latest01
# END_TIME=00:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-02
begin = 2023-02-02 00:02:28.319960306+00:00
start-sync_0 = 00:04:37
start-zstd = 00:06:02
start-sync_1 = 00:06:37
end-sync_1 = 00:06:48
end = 2023-02-02 00:06:48.181313731+00:00

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
