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
tag = ["zsh", "2022-01-13"]
os = "alpine"
release = "edge"
arch = "i386"
platform = "linux/386"
x11_or_wayland = false

[file]
name = "alpine-zsh_i386_2022-01-13_00-06.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "2390c4641a8723b26b941b6d2129637198f03121c7b81811715e7fa80652981c"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "94M"
tar_bytes = 98264064

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "28M"
zstd_bytes = 28732807

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220106"
previous_tag = "2022-01-06"
previous_file = "alpine-zsh_i386_2022-01-06_00-06-rootfs.tar.zst"
previous_sha256 = "f123bab47d5960f1fd357a108bbb783c17b624ad3378fa814eeb933bc4510f65"

current_version = "latest01"
current_date = "20220113"
old_file = "alpine-zsh_i386_2021-12-30_00-05-rootfs.tar.zst"
old_sha256 = "228b76d91bb70e6082a78db2438106e6d7824df9a1e355a4f989dca5e4733add"
# edition 2021
# DISTRO_NAME=alpine-edge_i386
# ROOTFS_FILE=alpine-zsh_i386_2022-01-13_00-06-rootfs.tar.zst
# SHA256SUM=2390c4641a8723b26b941b6d2129637198f03121c7b81811715e7fa80652981c
# BUILD_DATE=20220113
# BUILD_TAG=2022-01-13
# STATUS=completed
# VERSION=latest01
# END_TIME=00:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-13
begin = 2022-01-13 00:02:26.217085112+00:00
start-sync_0 = 00:03:59
start-zstd = 00:05:28
start-sync_1 = 00:06:02
end-sync_1 = 00:06:14
end = 2022-01-13 00:06:14.326063755+00:00

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
ldd = 'musl libc (i386) Version 1.2.2'
zsh = 'zsh 5.8 (i586-alpine-linux-musl)'
```
