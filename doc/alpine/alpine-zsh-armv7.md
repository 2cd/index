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
tag = ["zsh", "2022-06-23"]
os = "alpine"
release = "edge"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-zsh_armhf_2022-06-23_00-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "fc8ad164a50c8ca2b039185970187c45ef4f7e0028f98568b35b18b3baa901f3"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "76M"
tar_bytes = 78943744

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "27M"
zstd_bytes = 27528103

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220616"
previous_tag = "2022-06-16"
previous_file = "alpine-zsh_armhf_2022-06-16_00-05-rootfs.tar.zst"
previous_sha256 = "79b6911d80bf903731a0ba4c485cd46384ba84f221d342170c3053c7704cfee0"

current_version = "latest02"
current_date = "20220623"
old_file = "alpine-zsh_armhf_2022-06-09_00-05-rootfs.tar.zst"
old_sha256 = "4fea8f915972219fecec2ba8e9ddc5a3a5233c3c6ba98499f0e56440c840ce0f"
# edition 2021
# DISTRO_NAME=alpine-edge_armhf
# ROOTFS_FILE=alpine-zsh_armhf_2022-06-23_00-05-rootfs.tar.zst
# SHA256SUM=fc8ad164a50c8ca2b039185970187c45ef4f7e0028f98568b35b18b3baa901f3
# BUILD_DATE=20220623
# BUILD_TAG=2022-06-23
# STATUS=completed
# VERSION=latest02
# END_TIME=00:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-23
begin = 2022-06-23 00:02:30.840948489+00:00
start-sync_0 = 00:03:43
start-zstd = 00:05:04
start-sync_1 = 00:05:25
end-sync_1 = 00:05:31
end = 2022-06-23 00:05:31.314285036+00:00

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
