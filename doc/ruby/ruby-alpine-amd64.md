# ruby-alpine-amd64

## How to run it?

```sh
docker run \
    -it \
    --name ruby-alpine-amd64 \
    cake233/ruby-alpine-amd64
```

## How to exec shell?

```sh
docker exec -it ruby-alpine-amd64 bash
```

## ruby-alpine-amd64.toml

```toml
[main]
name = "ruby"
tag = ["alpine", "2022-11-21", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ruby-musl_amd64_2022-11-21_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a2f8bdba0cbb1b38ad82eaca42c0a85845041bb81c36c01aaa58a7b0d20cc0b9"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "83M"
tar_bytes = 86398464

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "33M"
zstd_bytes = 33833477

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221107"
previous_tag = "2022-11-07"
previous_file = "ruby-musl_amd64_2022-11-07_12-04-rootfs.tar.zst"
previous_sha256 = "9d12273e6b1669e4e41aa15d6144a6c1c657df8d8a179b37c240768bd21e06df"

current_version = "latest01"
current_date = "20221121"
old_file = "ruby-musl_amd64_2022-10-24_12-04-rootfs.tar.zst"
old_sha256 = "e26d09154d0e026c4fa0dd5dbccbeb3c488c5f4d5024b6626d6358743f1b0feb"
# edition 2021
# DISTRO_NAME=ruby_amd64
# ROOTFS_FILE=ruby-musl_amd64_2022-11-21_12-04-rootfs.tar.zst
# SHA256SUM=a2f8bdba0cbb1b38ad82eaca42c0a85845041bb81c36c01aaa58a7b0d20cc0b9
# BUILD_DATE=20221121
# BUILD_TAG=2022-11-21
# STATUS=completed
# VERSION=latest01
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-21
begin = 2022-11-21 12:02:29.482375144+00:00
start-sync_0 = 12:03:13
start-zstd = 12:03:20
start-sync_1 = 12:03:55
end-sync_1 = 12:04:01
end = 2022-11-21 12:04:01.440257206+00:00

[server]
repo = "cake233/ruby-alpine-amd64"

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
ldd = 'musl libc (x86_64) Version 1.2.3'
ruby = 'ruby 3.1.2p20 (2022-04-12 revision 4491bb740a) [x86_64-linux-musl]'
gem = '3.3.7'
bundle = 'Bundler version 2.3.7'
```
