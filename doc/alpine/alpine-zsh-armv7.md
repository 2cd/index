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
tag = ["zsh", "2022-05-26"]
os = "alpine"
release = "edge"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_armhf_2022-05-26_00-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "05d63eaf5b441a64f7c02e2532cab05a94b91a4d97fdaf370b978f34642f6901"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "76M"
tar_bytes = 78897664

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "27M"
zstd_bytes = 27489994

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220519"
previous_tag = "2022-05-19"
previous_file = "alpine-zsh_armhf_2022-05-19_00-05-rootfs.tar.zst"
previous_sha256 = "5335ee888dd4911fdae56ded5305c2fa46b7ae1763af27314ca9e9bfe0ce521d"

current_version = "latest02"
current_date = "20220526"
old_file = "alpine-zsh_armhf_2022-05-12_00-05-rootfs.tar.zst"
old_sha256 = "ced8da0409b7b005a2cc723b5694d23c4460a095fd277bc8c0fe3025365487b0"
# edition 2021
# DISTRO_NAME=alpine-edge_armhf
# ROOTFS_FILE=alpine-zsh_armhf_2022-05-26_00-05-rootfs.tar.zst
# SHA256SUM=05d63eaf5b441a64f7c02e2532cab05a94b91a4d97fdaf370b978f34642f6901
# BUILD_DATE=20220526
# BUILD_TAG=2022-05-26
# STATUS=completed
# VERSION=latest02
# END_TIME=00:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-26
begin = 2022-05-26 00:02:26.707973173+00:00
start-sync_0 = 00:03:49
start-zstd = 00:05:09
start-sync_1 = 00:05:37
end-sync_1 = 00:05:44
end = 2022-05-26 00:05:44.342442951+00:00

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
ldd = 'musl libc (armhf) Version 1.2.3'
zsh = 'zsh 5.8.1 (armv7-alpine-linux-musleabihf)'
```
