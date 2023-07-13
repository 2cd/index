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
tag = ["zsh", "2023-07-13"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_amd64_2023-07-13_00-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "cd6db454be91232f6bb5262995c1bb5df1cec87c97abe500d6f6e89f1c8f6035"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "93M"
tar_bytes = 96818688

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "31M"
zstd_bytes = 31740955

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230706"
previous_tag = "2023-07-06"
previous_file = "alpine-zsh_amd64_2023-07-06_00-04-rootfs.tar.zst"
previous_sha256 = "4bf24ea9266a685271cb4e50819619bbe8e8fd31d7aebe93f0cee7862e1933b8"

current_version = "latest01"
current_date = "20230713"
old_file = "alpine-zsh_amd64_2023-06-29_00-05-rootfs.tar.zst"
old_sha256 = "f2b872bab3e94f1393e9f4817cff76457039d863957e97122cf6b78d7fa6ad46"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-zsh_amd64_2023-07-13_00-05-rootfs.tar.zst
# SHA256SUM=cd6db454be91232f6bb5262995c1bb5df1cec87c97abe500d6f6e89f1c8f6035
# BUILD_DATE=20230713
# BUILD_TAG=2023-07-13
# STATUS=completed
# VERSION=latest01
# END_TIME=00:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-13
begin = 2023-07-13 00:02:33.245044187+00:00
start-sync_0 = 00:03:12
start-zstd = 00:04:38
start-sync_1 = 00:05:14
end-sync_1 = 00:05:24
end = 2023-07-13 00:05:24.584921110+00:00

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
ldd = 'musl libc (x86_64) Version 1.2.4'
zsh = 'zsh 5.9 (x86_64-alpine-linux-musl)'
```
