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
tag = ["zsh", "2022-06-08"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_arm64_2022-06-08_12-20.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "2c0d8a0d2717a4da1acc28e9d76f4a8527d9c234b100db1384ef39739d6182cb"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "745M"
tar_bytes = 780780032

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "146M"
zstd_bytes = 152335466

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220601"
previous_tag = "2022-06-01"
previous_file = "debian-zsh_arm64_2022-06-01_12-17-rootfs.tar.zst"
previous_sha256 = "38c35b58d6385238bedc80b211daffa6249adb3362faca66cff86e249a247680"

current_version = "latest01"
current_date = "20220608"
old_file = "debian-zsh_arm64_2022-05-25_12-19-rootfs.tar.zst"
old_sha256 = "731657455e9f3f9df03913a8f2b717f2fc076cd67c65c99a0a744b035cf71711"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-zsh_arm64_2022-06-08_12-20-rootfs.tar.zst
# SHA256SUM=2c0d8a0d2717a4da1acc28e9d76f4a8527d9c234b100db1384ef39739d6182cb
# BUILD_DATE=20220608
# BUILD_TAG=2022-06-08
# STATUS=completed
# VERSION=latest01
# END_TIME=12:20

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-08
begin = 2022-06-08 12:02:37.130946037+00:00
start-sync_0 = 12:16:01
start-zstd = 12:17:49
start-sync_1 = 12:20:22
end-sync_1 = 12:20:36
end = 2022-06-08 12:20:36.656930080+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-7) 2.33'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'
```
