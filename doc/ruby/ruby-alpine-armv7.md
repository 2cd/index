# ruby-alpine-armv7

## How to run it?

```sh
docker run \
    -it \
    --name ruby-alpine-armv7 \
    cake233/ruby-alpine-armv7
```

## How to exec shell?

```sh
docker exec -it ruby-alpine-armv7 bash
```

## ruby-alpine-armv7.toml

```toml
[main]
name = "ruby"
tag = ["alpine", "2023-02-27", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ruby-musl_armhf_2023-02-27_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f9a5d3baba7970552c3fd59605e4409c8197494cfc8cda9ef133c644c8c88c6d"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "88M"
tar_bytes = 91724800

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "33M"
zstd_bytes = 33711757

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230213"
previous_tag = "2023-02-13"
previous_file = "ruby-musl_armhf_2023-02-13_12-04-rootfs.tar.zst"
previous_sha256 = "cfa78495fa25bdf0fc21f8d63689dbd60f97035abf71b8051a8c4fa56801bbd5"

current_version = "latest01"
current_date = "20230227"
old_file = "ruby-musl_armhf_2023-01-30_12-04-rootfs.tar.zst"
old_sha256 = "519ebbce610db83ba1a349ae99cb5e6d183a96a65d67577b11b6b7288f40163d"
# edition 2021
# DISTRO_NAME=ruby_armhf
# ROOTFS_FILE=ruby-musl_armhf_2023-02-27_12-04-rootfs.tar.zst
# SHA256SUM=f9a5d3baba7970552c3fd59605e4409c8197494cfc8cda9ef133c644c8c88c6d
# BUILD_DATE=20230227
# BUILD_TAG=2023-02-27
# STATUS=completed
# VERSION=latest01
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-27
begin = 2023-02-27 12:02:41.503110000+00:00
start-sync_0 = 12:03:40
start-zstd = 12:03:48
start-sync_1 = 12:04:20
end-sync_1 = 12:04:29
end = 2023-02-27 12:04:29.217855724+00:00

[server]
repo = "cake233/ruby-alpine-armv7"

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
PATH = "/usr/local/bundle/bin${PATH:+:${PATH}}"
GEM_HOME = '/usr/local/bundle'
BUNDLE_SILENCE_ROOT_WARNING = '1'
BUNDLE_APP_CONFIG = '/usr/local/bundle'

[version]
ldd = 'musl libc (armhf) Version 1.2.3'
ruby = 'ruby 3.2.1 (2023-02-08 revision 31819e82c8) [arm-linux-musleabihf]'
gem = '3.4.6'
bundle = 'Bundler version 2.4.6'
```
