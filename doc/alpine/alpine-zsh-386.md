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
tag = ["zsh", "2023-04-20"]
os = "alpine"
release = "edge"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_i386_2023-04-20_00-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "3770a91336766bb67afd5069697bd9edeb21da83bf1c0995da74634482aa01e3"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "95M"
tar_bytes = 98781696

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "31M"
zstd_bytes = 32353977

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230413"
previous_tag = "2023-04-13"
previous_file = "alpine-zsh_i386_2023-04-13_00-06-rootfs.tar.zst"
previous_sha256 = "77d9af393d5498a8664585cc71e6526f36bdec66a567a8aab641229691222bff"

current_version = "latest02"
current_date = "20230420"
old_file = "alpine-zsh_i386_2023-04-06_00-06-rootfs.tar.zst"
old_sha256 = "eba9930752a7ad72ba42a17e26f59013a2704f83ffde6fe28ee194c2e6c822d9"
# edition 2021
# DISTRO_NAME=alpine-edge_i386
# ROOTFS_FILE=alpine-zsh_i386_2023-04-20_00-06-rootfs.tar.zst
# SHA256SUM=3770a91336766bb67afd5069697bd9edeb21da83bf1c0995da74634482aa01e3
# BUILD_DATE=20230420
# BUILD_TAG=2023-04-20
# STATUS=completed
# VERSION=latest02
# END_TIME=00:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-20
begin = 2023-04-20 00:02:30.584064653+00:00
start-sync_0 = 00:04:01
start-zstd = 00:05:24
start-sync_1 = 00:05:52
end-sync_1 = 00:06:00
end = 2023-04-20 00:06:00.880769210+00:00

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
ldd = 'musl libc (i386) Version 1.2.3_git20230411'
zsh = 'zsh 5.9 (i586-alpine-linux-musl)'
```
