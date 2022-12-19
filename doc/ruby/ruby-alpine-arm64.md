# ruby-alpine-arm64

## How to run it?

```sh
docker run \
    -it \
    --name ruby-alpine-arm64 \
    cake233/ruby-alpine-arm64
```

## How to exec shell?

```sh
docker exec -it ruby-alpine-arm64 bash
```

## ruby-alpine-arm64.toml

```toml
[main]
name = "ruby"
tag = ["alpine", "2022-12-19", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ruby-musl_arm64_2022-12-19_19-14.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "26d194935245d3356669290495b3b262795a01f02fc77ddcf92c3718b9cafe11"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "100M"
tar_bytes = 103917568

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "33M"
zstd_bytes = 33967158

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221205"
previous_tag = "2022-12-05"
previous_file = "ruby-musl_arm64_2022-12-05_12-04-rootfs.tar.zst"
previous_sha256 = "1875c6dc88a4932d8c3446b642a3e9624a2de419c4c4cbe5adaa0fa9b2d285fd"

current_version = "latest01"
current_date = "20221219"
old_file = "ruby-musl_arm64_2022-11-21_12-04-rootfs.tar.zst"
old_sha256 = "c9b8aed9af20527993a5a99441d0b0345eb3d32ead40358d603b8c91f687e184"
# edition 2021
# DISTRO_NAME=ruby_arm64
# ROOTFS_FILE=ruby-musl_arm64_2022-12-19_19-14-rootfs.tar.zst
# SHA256SUM=26d194935245d3356669290495b3b262795a01f02fc77ddcf92c3718b9cafe11
# BUILD_DATE=20221219
# BUILD_TAG=2022-12-19
# STATUS=completed
# VERSION=latest01
# END_TIME=19:14

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-19
begin = 2022-12-19 19:12:25.389770751+00:00
start-sync_0 = 19:13:08
start-zstd = 19:13:17
start-sync_1 = 19:14:03
end-sync_1 = 19:14:12
end = 2022-12-19 19:14:12.883411637+00:00

[server]
repo = "cake233/ruby-alpine-arm64"

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
ldd = 'musl libc (aarch64) Version 1.2.3'
ruby = 'ruby 3.1.3p185 (2022-11-24 revision 1a6b16756e) [aarch64-linux-musl]'
gem = '3.3.26'
bundle = 'Bundler version 2.3.26'
```
