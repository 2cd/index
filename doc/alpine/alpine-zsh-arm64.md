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
tag = ["zsh", "2023-08-31"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_arm64_2023-08-31_00-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "283629bfa50414a565a89da94ee672a15351688d5e49d8f4e51ae1efc0c605a8"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "150M"
tar_bytes = 156850176

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "37M"
zstd_bytes = 38739011

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230824"
previous_tag = "2023-08-24"
previous_file = "alpine-zsh_arm64_2023-08-24_00-06-rootfs.tar.zst"
previous_sha256 = "7e19ba261ae5b0b03e983484b576d680c3cb62c4f348b31d9101209a64637f2f"

current_version = "latest01"
current_date = "20230831"
old_file = "alpine-zsh_arm64_2023-08-17_00-06-rootfs.tar.zst"
old_sha256 = "992e8635d610e2d1943a89793cdf4a0181c3da2ef3519430ebef6b240dd058be"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-zsh_arm64_2023-08-31_00-07-rootfs.tar.zst
# SHA256SUM=283629bfa50414a565a89da94ee672a15351688d5e49d8f4e51ae1efc0c605a8
# BUILD_DATE=20230831
# BUILD_TAG=2023-08-31
# STATUS=completed
# VERSION=latest01
# END_TIME=00:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-31
begin = 2023-08-31 00:02:35.506949122+00:00
start-sync_0 = 00:05:07
start-zstd = 00:06:31
start-sync_1 = 00:07:15
end-sync_1 = 00:07:23
end = 2023-08-31 00:07:23.978394467+00:00

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
ldd = 'musl libc (aarch64) Version 1.2.4_git20230717'
zsh = 'zsh 5.9 (aarch64-alpine-linux-musl)'
```
