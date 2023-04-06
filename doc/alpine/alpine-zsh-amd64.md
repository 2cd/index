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
tag = ["zsh", "2023-04-06"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_amd64_2023-04-06_00-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "90065c0c0eb8ab3d115f6fabc421b8f8613e19a517705b5429078bee29d654e6"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "97M"
tar_bytes = 100915200

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "32M"
zstd_bytes = 32573378

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230330"
previous_tag = "2023-03-30"
previous_file = "alpine-zsh_amd64_2023-03-30_00-05-rootfs.tar.zst"
previous_sha256 = "a962468a9b6142a683453c2fd4ba8f956faf95a8e87f6f164f4b5ba59090f00c"

current_version = "latest01"
current_date = "20230406"
old_file = "alpine-zsh_amd64_2023-03-23_00-05-rootfs.tar.zst"
old_sha256 = "dd1966a9a82d589e10d8170e60d4b1b1c2987c408e0981f1329a9cfba5e60551"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-zsh_amd64_2023-04-06_00-05-rootfs.tar.zst
# SHA256SUM=90065c0c0eb8ab3d115f6fabc421b8f8613e19a517705b5429078bee29d654e6
# BUILD_DATE=20230406
# BUILD_TAG=2023-04-06
# STATUS=completed
# VERSION=latest01
# END_TIME=00:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-06
begin = 2023-04-06 00:02:23.133076701+00:00
start-sync_0 = 00:03:00
start-zstd = 00:04:22
start-sync_1 = 00:04:56
end-sync_1 = 00:05:04
end = 2023-04-06 00:05:04.595450617+00:00

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
