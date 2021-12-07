# ubuntu-zsh-arm64

## How to run it?

```shell
docker run \
    -it \
    --name ubuntu-zsh-arm64 \
    cake233/ubuntu-zsh-arm64
```

## How to exec shell?

```shell
    docker exec -it ubuntu-zsh-arm64 zsh
```

## ubuntu-zsh-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["zsh", "2021-12-07", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "ubuntu-zsh_arm64_2021-12-07_00-22.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "22dca6b25452c415a08ca8199dbe949a7df457548d70c4aa38e3fc81ea91c4a8"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "615M"
tar_bytes = 644496384

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "110M"
zstd_bytes = 114505839

[compatibility]
compatible_mode = true

last_version = "latest01"

# The value is &str, not int
last_date = "20211130"
last_tag = "2021-11-30"
last_file = "ubuntu-zsh_arm64_2021-11-30_13-42-rootfs.tar.zst"
last_sha256 = ""

current_version = "latest02"
current_date = "20211207"
old_file = "ubuntu-zsh-arm64_2021-11-28_21-09-rootfs.tar.zst"
old_sha256 = ""
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-zsh_arm64_2021-12-07_00-22-rootfs.tar.zst
# SHA256SUM=22dca6b25452c415a08ca8199dbe949a7df457548d70c4aa38e3fc81ea91c4a8
# BUILD_DATE=20211207
# BUILD_TAG=2021-12-07
# STATUS=completed
# VERSION=latest02
# END_TIME=00:22

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-07
begin = 2021-12-07 00:02:27.877514406+00:00
start-sync_0 = 00:17:53
start-zstd = 00:19:42
start-sync_1 = 00:22:32
end-sync_1 = 00:22:46
end = 2021-12-07 00:22:46.152495797+00:00

[server]
repo = "cake233/ubuntu-zsh-arm64"

[server.node1]
name = "cn"
current = false
last = true
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = false
last = true
in_sync = false
split = false

[server.node3]
name = "azure"
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
