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
tag = ["zsh", "2022-08-09"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-zsh_arm64_2022-08-09_12-43.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "9b6c96f78133b2a43f8b67d5091819a02972503f359a13b97c774762f8518898"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1130817536

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "175M"
zstd_bytes = 183026458

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220712"
previous_tag = "2022-07-12"
previous_file = "fedora-zsh_arm64_2022-07-12_12-42-rootfs.tar.zst"
previous_sha256 = "b1d14d840fbd9497526a3de37ed28fe8f5ee2a211655f35959f5fe262e5d03d8"

current_version = "latest01"
current_date = "20220809"
old_file = "fedora-zsh_arm64_2022-07-05_12-42-rootfs.tar.zst"
old_sha256 = "16a5f227e7d5cdcea901cd2aa0ff4cda0845bc5cdd972bf93bd88a671c26af27"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-zsh_arm64_2022-08-09_12-43-rootfs.tar.zst
# SHA256SUM=9b6c96f78133b2a43f8b67d5091819a02972503f359a13b97c774762f8518898
# BUILD_DATE=20220809
# BUILD_TAG=2022-08-09
# STATUS=completed
# VERSION=latest01
# END_TIME=12:43

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-09
begin = 2022-08-09 12:02:23.628965565+00:00
start-sync_0 = 12:38:27
start-zstd = 12:40:24
start-sync_1 = 12:43:40
end-sync_1 = 12:43:55
end = 2022-08-09 12:43:55.797006329+00:00

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
ldd = 'ldd (GNU libc) 2.36'
zsh = 'zsh 5.9 (aarch64-redhat-linux-gnu)'
```
