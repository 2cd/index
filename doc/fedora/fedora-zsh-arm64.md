# fedora-zsh-arm64

## How to run it?

```shell
docker run \
    -it \
    --name fedora-zsh-arm64 \
    cake233/fedora-zsh-arm64
```

## How to exec shell?

```shell
    docker exec -it fedora-zsh-arm64 zsh
```

## fedora-zsh-arm64.toml

```toml
[main]
name = "fedora"
tag = ["zsh", "2021-11-30"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "fedora-zsh_arm64_2021-11-30_12-42.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "69344d0aedd69c3ea49a469c2e2994d2546fe6402725e5df27c077ffeb09b188"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.2G"
tar_bytes = 1245372416

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "208M"
zstd_bytes = 217152863

[compatibility]
compatible_mode = true

last_version = "latest01"

# The value is &str, not int
last_date = "20211128"
last_tag = "2021-11-28"
last_file = "fedora-zsh-arm64_2021-11-28_21-29-rootfs.tar.zst"

current_version = "latest02"
current_date = "20211130"
old_file = "fedora-rawhide_arm64+zsh-2021_11-02-rootfs.tar.zst"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-zsh_arm64_2021-11-30_12-42-rootfs.tar.zst
# BUILD_DATE=20211130
# BUILD_TAG=2021-11-30
# STATUS=completed
# VERSION=latest02
# END_TIME=12:42

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-11-30
begin = 2021-11-30 12:01:51.467364579+00:00
start-sync_0 = 12:36:58
start-zstd = 12:39:01
start-sync_1 = 12:42:30
end-sync_1 = 12:42:50
end = 2021-11-30 12:42:50.164063545+00:00

[server]
repo = "cake233/fedora-zsh-arm64"

[server.node1]
name = "cn"
current = false
last = true
in_sync = false
split = false

[server.node2]
name = "us"
current = false
last = true
in_sync = false
split = false

[server.node3]
name = "global"
current = false
last = true
in_sync = false
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"
```
