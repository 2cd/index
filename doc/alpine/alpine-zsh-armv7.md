# alpine-zsh-armv7

## How to run it?

```sh
docker run \
    -it \
    --name alpine-zsh-armv7 \
    cake233/alpine-zsh-armv7
```

## How to exec shell?

```sh
docker exec -it alpine-zsh-armv7 zsh
```

## alpine-zsh-armv7.toml

```toml
[main]
name = "alpine"
tag = ["zsh", "2023-05-18"]
os = "alpine"
release = "edge"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_armhf_2023-05-18_00-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d78038f1fed7fae74164b90bbfbc3bbb6f136513af916f983da83f820ec86174"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "76M"
tar_bytes = 79479296

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "29M"
zstd_bytes = 30054843

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230511"
previous_tag = "2023-05-11"
previous_file = "alpine-zsh_armhf_2023-05-11_00-05-rootfs.tar.zst"
previous_sha256 = "7606684d6e63100e744f2f40220a76e6308ec8bb86159c3e138eef2826492c3e"

current_version = "latest02"
current_date = "20230518"
old_file = "alpine-zsh_armhf_2023-05-04_00-06-rootfs.tar.zst"
old_sha256 = "660fe6c15370f6f82c346abe842a4e7870bd3c3415a9472d2aa3d26df80caea2"
# edition 2021
# DISTRO_NAME=alpine-edge_armhf
# ROOTFS_FILE=alpine-zsh_armhf_2023-05-18_00-05-rootfs.tar.zst
# SHA256SUM=d78038f1fed7fae74164b90bbfbc3bbb6f136513af916f983da83f820ec86174
# BUILD_DATE=20230518
# BUILD_TAG=2023-05-18
# STATUS=completed
# VERSION=latest02
# END_TIME=00:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-05-18
begin = 2023-05-18 00:02:30.942221666+00:00
start-sync_0 = 00:04:08
start-zstd = 00:05:28
start-sync_1 = 00:05:52
end-sync_1 = 00:05:58
end = 2023-05-18 00:05:58.046494268+00:00

[server]
repo = "cake233/alpine-zsh-armv7"

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
LANG = "C.UTF-8"

[version]
ldd = 'musl libc (armhf) Version 1.2.4'
zsh = 'zsh 5.9 (armv7-alpine-linux-musleabihf)'
```
