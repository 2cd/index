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
tag = ["alpine", "2022-07-04", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ruby-musl_armhf_2022-07-04_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "42ef6d2dfd1f05fdc24bfcbf46a6d2a10fc7493ee229d57e2e4736e8a5be17f1"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "73M"
tar_bytes = 75675648

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "31M"
zstd_bytes = 31790649

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220620"
previous_tag = "2022-06-20"
previous_file = "ruby-musl_armhf_2022-06-20_12-04-rootfs.tar.zst"
previous_sha256 = "62f71bb5a4d69f117599b648c42b79f2d2ee00e98bb884f4dcb2e72610e5bc18"

current_version = "latest02"
current_date = "20220704"
old_file = "ruby-musl_armhf_2022-06-06_12-04-rootfs.tar.zst"
old_sha256 = "08702cddf5eb7f46638d2c3427ad3cb12e9a67edd05eef09b8b88344167a37b9"
# edition 2021
# DISTRO_NAME=ruby_armhf
# ROOTFS_FILE=ruby-musl_armhf_2022-07-04_12-04-rootfs.tar.zst
# SHA256SUM=42ef6d2dfd1f05fdc24bfcbf46a6d2a10fc7493ee229d57e2e4736e8a5be17f1
# BUILD_DATE=20220704
# BUILD_TAG=2022-07-04
# STATUS=completed
# VERSION=latest02
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-04
begin = 2022-07-04 12:02:36.340062697+00:00
start-sync_0 = 12:03:45
start-zstd = 12:03:55
start-sync_1 = 12:04:31
end-sync_1 = 12:04:41
end = 2022-07-04 12:04:41.461619245+00:00

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
ruby = 'ruby 3.1.2p20 (2022-04-12 revision 4491bb740a) [arm-linux-musleabihf]'
gem = '3.3.7'
bundle = 'Bundler version 2.3.7'
```
