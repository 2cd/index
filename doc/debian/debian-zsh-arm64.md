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
tag = ["zsh", "2023-07-19"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_arm64_2023-07-19_12-20.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5d4553a73a23f810b487c9a903a0befbf108ff495d7842603a822fbfa5db62f4"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "818M"
tar_bytes = 857193472

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "150M"
zstd_bytes = 156937549

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230712"
previous_tag = "2023-07-12"
previous_file = "debian-zsh_arm64_2023-07-12_12-20-rootfs.tar.zst"
previous_sha256 = "e4aaaae4f3721753e4d64b4a431635515c2fcc157582c551470c8976a9d9baaf"

current_version = "latest02"
current_date = "20230719"
old_file = "debian-zsh_arm64_2023-07-05_12-14-rootfs.tar.zst"
old_sha256 = "69029b0cc7ef4b3b2d184913b4981671f39f10a2f8d3ddee2d94745e826cf808"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-zsh_arm64_2023-07-19_12-20-rootfs.tar.zst
# SHA256SUM=5d4553a73a23f810b487c9a903a0befbf108ff495d7842603a822fbfa5db62f4
# BUILD_DATE=20230719
# BUILD_TAG=2023-07-19
# STATUS=completed
# VERSION=latest02
# END_TIME=12:20

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-19
begin = 2023-07-19 12:02:33.605203490+00:00
start-sync_0 = 12:15:52
start-zstd = 12:17:49
start-sync_1 = 12:20:33
end-sync_1 = 12:20:52
end = 2023-07-19 12:20:52.420269811+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-6) 2.37'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'
```
