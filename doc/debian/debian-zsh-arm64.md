# debian-zsh-arm64

## How to run it?

```sh
docker run \
    -it \
    --name debian-zsh-arm64 \
    cake233/debian-zsh-arm64
```

## How to exec shell?

```sh
docker exec -it debian-zsh-arm64 zsh
```

## debian-zsh-arm64.toml

```toml
[main]
name = "debian"
tag = ["zsh", "2023-08-30"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_arm64_2023-08-30_12-24.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "05e2ba5a9b45a8437ad05380b72765745bba4a088f1bc8207a3aadfd8d2856c7"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "859M"
tar_bytes = 900127744

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "162M"
zstd_bytes = 169439272

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20230830"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-zsh_arm64_2023-08-30_12-24-rootfs.tar.zst
# SHA256SUM=05e2ba5a9b45a8437ad05380b72765745bba4a088f1bc8207a3aadfd8d2856c7
# BUILD_DATE=20230830
# BUILD_TAG=2023-08-30
# STATUS=completed
# VERSION=latest01
# END_TIME=12:24

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-30
begin = 2023-08-30 12:02:46.746775879+00:00
start-sync_0 = 12:19:02
start-zstd = 12:20:59
start-sync_1 = 12:24:35
end-sync_1 = 12:24:54
end = 2023-08-30 12:24:54.384940757+00:00

[server]
repo = "cake233/debian-zsh-arm64"

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
ldd = 'ldd (Debian GLIBC 2.37-7) 2.37'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'
```
