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
tag = ["zsh", "2023-06-01"]
os = "alpine"
release = "edge"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_armhf_2023-06-01_00-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8ecf4a966969aabae453e51be5b1a0a1460e49ac4e8b268fc863283cb823d444"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "77M"
tar_bytes = 80479744

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "29M"
zstd_bytes = 30270254

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230525"
previous_tag = "2023-05-25"
previous_file = "alpine-zsh_armhf_2023-05-25_00-06-rootfs.tar.zst"
previous_sha256 = "2c180cac3fa0698c94fc489cceef3572dd2766b08975782cee7710c6bc03db30"

current_version = "latest02"
current_date = "20230601"
old_file = "alpine-zsh_armhf_2023-05-18_00-05-rootfs.tar.zst"
old_sha256 = "d78038f1fed7fae74164b90bbfbc3bbb6f136513af916f983da83f820ec86174"
# edition 2021
# DISTRO_NAME=alpine-edge_armhf
# ROOTFS_FILE=alpine-zsh_armhf_2023-06-01_00-05-rootfs.tar.zst
# SHA256SUM=8ecf4a966969aabae453e51be5b1a0a1460e49ac4e8b268fc863283cb823d444
# BUILD_DATE=20230601
# BUILD_TAG=2023-06-01
# STATUS=completed
# VERSION=latest02
# END_TIME=00:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-01
begin = 2023-06-01 00:02:29.248074029+00:00
start-sync_0 = 00:03:59
start-zstd = 00:05:19
start-sync_1 = 00:05:42
end-sync_1 = 00:05:48
end = 2023-06-01 00:05:48.770319269+00:00

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
