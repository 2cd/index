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
tag = ["zsh", "2022-03-23"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "debian-zsh_arm64_2022-03-23_12-17.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "2156d0270fd6df3399f47a208fca3492ed5d8045d9288c81799f65430729414f"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "737M"
tar_bytes = 772454400

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "143M"
zstd_bytes = 149490060

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220316"
previous_tag = "2022-03-16"
previous_file = "debian-zsh_arm64_2022-03-16_12-21-rootfs.tar.zst"
previous_sha256 = "228bf2ab71c550fff9f8cb12c76f9791d07ace6cc7d46b0dff453c8ac1b5ce8a"

current_version = "latest02"
current_date = "20220323"
old_file = "debian-zsh_arm64_2022-03-09_12-20-rootfs.tar.zst"
old_sha256 = "3852111216ff09f3a12543593e88d5693f56f52d2db22a272335e554740aac2c"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-zsh_arm64_2022-03-23_12-17-rootfs.tar.zst
# SHA256SUM=2156d0270fd6df3399f47a208fca3492ed5d8045d9288c81799f65430729414f
# BUILD_DATE=20220323
# BUILD_TAG=2022-03-23
# STATUS=completed
# VERSION=latest02
# END_TIME=12:17

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-23
begin = 2022-03-23 12:02:35.777266193+00:00
start-sync_0 = 12:13:08
start-zstd = 12:14:55
start-sync_1 = 12:17:03
end-sync_1 = 12:17:20
end = 2022-03-23 12:17:20.070113563+00:00

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
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
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
ldd = 'ldd (Debian GLIBC 2.33-7) 2.33'
zsh = 'zsh 5.8.1 (aarch64-unknown-linux-gnu)'
```
