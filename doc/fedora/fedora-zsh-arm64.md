# fedora-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name fedora-zsh-arm64 \
    cake233/fedora-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it fedora-zsh-arm64 zsh
```

## fedora-zsh-arm64.toml

```toml
[main]
name = "fedora"
tag = ["zsh", "2023-10-17"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-zsh_arm64_2023-10-17_13-01.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "6161e29fd2136c63c09b07006dbe7a6916b1ba56a61e81f56659fe3e95b8f9ad"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1556839424

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "221M"
zstd_bytes = 231120611

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231010"
previous_tag = "2023-10-10"
previous_file = "fedora-zsh_arm64_2023-10-10_12-47-rootfs.tar.zst"
previous_sha256 = "6cc6df9a30b2e76fb5ded80cfc1d072bbf75215dae3eb6d9bf6549d713c71c57"

current_version = "latest02"
current_date = "20231017"
old_file = "fedora-zsh_arm64_2023-10-03_12-51-rootfs.tar.zst"
old_sha256 = "4191e4537c89a5e08df6cd059d32c7eddf33d928121a7e35b7d6caeb72584e7c"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-zsh_arm64_2023-10-17_13-01-rootfs.tar.zst
# SHA256SUM=6161e29fd2136c63c09b07006dbe7a6916b1ba56a61e81f56659fe3e95b8f9ad
# BUILD_DATE=20231017
# BUILD_TAG=2023-10-17
# STATUS=completed
# VERSION=latest02
# END_TIME=13:01

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-17
begin = 2023-10-17 12:02:39.511798180+00:00
start-sync_0 = 12:53:24
start-zstd = 12:55:42
start-sync_1 = 13:00:36
end-sync_1 = 13:01:05
end = 2023-10-17 13:01:05.712796459+00:00

[server]
repo = "cake233/fedora-zsh-arm64"

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
LANG = "en_US.UTF-8"

[version]
ldd = 'ldd (GNU libc) 2.38.9000'
zsh = 'zsh 5.9 (aarch64-redhat-linux-gnu)'
```
