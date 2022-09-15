# alpine-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name alpine-zsh-arm64 \
    cake233/alpine-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it alpine-zsh-arm64 zsh
```

## alpine-zsh-arm64.toml

```toml
[main]
name = "alpine"
tag = ["zsh", "2022-09-15"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_arm64_2022-09-15_00-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b55e5f2b239d0c7a432490c37c9dc9fbd0c1d1125efb7baf944fd3535af730a9"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "101M"
tar_bytes = 104974848

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "29M"
zstd_bytes = 29979557

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220908"
previous_tag = "2022-09-08"
previous_file = "alpine-zsh_arm64_2022-09-08_00-06-rootfs.tar.zst"
previous_sha256 = "d28368d694e898586ad2818d80f51f05602a5eb6dcea582f647aedd8d1f23ed5"

current_version = "latest02"
current_date = "20220915"
old_file = "alpine-zsh_arm64_2022-09-01_00-06-rootfs.tar.zst"
old_sha256 = "6c493153afbbb463781490627df0f6f075ac770dedd60b302cd4ee8d703099b3"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-zsh_arm64_2022-09-15_00-05-rootfs.tar.zst
# SHA256SUM=b55e5f2b239d0c7a432490c37c9dc9fbd0c1d1125efb7baf944fd3535af730a9
# BUILD_DATE=20220915
# BUILD_TAG=2022-09-15
# STATUS=completed
# VERSION=latest02
# END_TIME=00:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-15
begin = 2022-09-15 00:02:19.835753229+00:00
start-sync_0 = 00:03:47
start-zstd = 00:05:09
start-sync_1 = 00:05:39
end-sync_1 = 00:05:44
end = 2022-09-15 00:05:45.013865706+00:00

[server]
repo = "cake233/alpine-zsh-arm64"

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
ldd = 'musl libc (aarch64) Version 1.2.3'
zsh = 'zsh 5.9 (aarch64-alpine-linux-musl)'
```
