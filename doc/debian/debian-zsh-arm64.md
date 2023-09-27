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
tag = ["zsh", "2023-09-27"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_arm64_2023-09-27_12-31.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "0acf7298d123df0f9b5ce92d58a80863bcd5552c3311a71a76850a3d33228ef9"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "817M"
tar_bytes = 856159744

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "150M"
zstd_bytes = 156334301

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230920"
previous_tag = "2023-09-20"
previous_file = "debian-zsh_arm64_2023-09-20_12-31-rootfs.tar.zst"
previous_sha256 = "ddfa5921154b21a34b93a70d89843c8c2edc179d40e49df16b91ebce48648462"

current_version = "latest01"
current_date = "20230927"
old_file = "debian-zsh_arm64_2023-09-13_12-22-rootfs.tar.zst"
old_sha256 = "99d4f2d842b4b5e9292cb26cbd686624dbc215ca3e4b79f027efd17b009e768f"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-zsh_arm64_2023-09-27_12-31-rootfs.tar.zst
# SHA256SUM=0acf7298d123df0f9b5ce92d58a80863bcd5552c3311a71a76850a3d33228ef9
# BUILD_DATE=20230927
# BUILD_TAG=2023-09-27
# STATUS=completed
# VERSION=latest01
# END_TIME=12:31

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-27
begin = 2023-09-27 12:02:37.098831380+00:00
start-sync_0 = 12:26:53
start-zstd = 12:28:40
start-sync_1 = 12:31:22
end-sync_1 = 12:31:41
end = 2023-09-27 12:31:41.610952627+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-10) 2.37'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'
```
