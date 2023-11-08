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
tag = ["zsh", "2023-11-08"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_arm64_2023-11-08_12-31.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "e5c1e24b4634ed93bdf1fb2d56ad24de1097762feaa8d5070ac5ea79daf71353"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "820M"
tar_bytes = 859711488

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "150M"
zstd_bytes = 156856839

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231025"
previous_tag = "2023-10-25"
previous_file = "debian-zsh_arm64_2023-10-25_12-46-rootfs.tar.zst"
previous_sha256 = "18b02bc6b8d33e02fa50f3b35a291854814448d59191d640ab6ffd4e9bca9aa6"

current_version = "latest02"
current_date = "20231108"
old_file = "debian-zsh_arm64_2023-10-18_12-45-rootfs.tar.zst"
old_sha256 = "046d1da0759b63600cd2c8b0cabfaf0fb3f0d747a03d209e0a67b5827fca6d59"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-zsh_arm64_2023-11-08_12-31-rootfs.tar.zst
# SHA256SUM=e5c1e24b4634ed93bdf1fb2d56ad24de1097762feaa8d5070ac5ea79daf71353
# BUILD_DATE=20231108
# BUILD_TAG=2023-11-08
# STATUS=completed
# VERSION=latest02
# END_TIME=12:31

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-11-08
begin = 2023-11-08 12:02:33.545562862+00:00
start-sync_0 = 12:27:06
start-zstd = 12:28:44
start-sync_1 = 12:30:54
end-sync_1 = 12:31:10
end = 2023-11-08 12:31:10.368714011+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-12) 2.37'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'
```
