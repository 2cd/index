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
tag = ["zsh", "2022-05-11"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_arm64_2022-05-11_12-17.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "babe208fcfe424c7d7f15b6a82310038430200f2f9d7837cb95e43c83b895b88"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "742M"
tar_bytes = 777407488

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "144M"
zstd_bytes = 150668247

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220504"
previous_tag = "2022-05-04"
previous_file = "debian-zsh_arm64_2022-05-04_12-20-rootfs.tar.zst"
previous_sha256 = "9d8cfd1e196b894b66fc966fb0985f0c649df2a30d18a10688cd4cf3fd76af12"

current_version = "latest01"
current_date = "20220511"
old_file = "debian-zsh_arm64_2022-04-27_12-22-rootfs.tar.zst"
old_sha256 = "9ce0cb28737f41d0d92a4d6ebd62afb04d61a418ca22b6d46e6e02a54225b221"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-zsh_arm64_2022-05-11_12-17-rootfs.tar.zst
# SHA256SUM=babe208fcfe424c7d7f15b6a82310038430200f2f9d7837cb95e43c83b895b88
# BUILD_DATE=20220511
# BUILD_TAG=2022-05-11
# STATUS=completed
# VERSION=latest01
# END_TIME=12:17

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-11
begin = 2022-05-11 12:02:43.438195068+00:00
start-sync_0 = 12:13:27
start-zstd = 12:15:11
start-sync_1 = 12:17:43
end-sync_1 = 12:17:57
end = 2022-05-11 12:17:57.794180949+00:00

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
zsh = 'zsh 5.8.1 (aarch64-unknown-linux-gnu)'
```
