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
tag = ["zsh", "2022-10-19"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_arm64_2022-10-19_12-13.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d41396b5557488ddd3b3544df49bb0b7c1ac903dcaf29bf01271917f32f7f128"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "674M"
tar_bytes = 706055168

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "118M"
zstd_bytes = 123552466

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221012"
previous_tag = "2022-10-12"
previous_file = "debian-zsh_arm64_2022-10-12_12-19-rootfs.tar.zst"
previous_sha256 = "9ffe268c956e6e763147f2e1dab94a55c307e81b7a82ae2351950459e3d60176"

current_version = "latest01"
current_date = "20221019"
old_file = "debian-zsh_arm64_2022-10-05_12-22-rootfs.tar.zst"
old_sha256 = "0409ba547a846648852d86114ec402378e63a6f0db946c27304761726424c6f7"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-zsh_arm64_2022-10-19_12-13-rootfs.tar.zst
# SHA256SUM=d41396b5557488ddd3b3544df49bb0b7c1ac903dcaf29bf01271917f32f7f128
# BUILD_DATE=20221019
# BUILD_TAG=2022-10-19
# STATUS=completed
# VERSION=latest01
# END_TIME=12:13

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-19
begin = 2022-10-19 12:02:21.455731121+00:00
start-sync_0 = 12:10:35
start-zstd = 12:11:06
start-sync_1 = 12:13:00
end-sync_1 = 12:13:11
end = 2022-10-19 12:13:11.867644013+00:00

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
ldd = 'ldd (Debian GLIBC 2.35-3) 2.35'
zsh = ''
```
