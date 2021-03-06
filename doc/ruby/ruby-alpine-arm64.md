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
tag = ["alpine", "2022-07-18", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ruby-musl_arm64_2022-07-18_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "cf6072bf27cdf037229654fba25510976d600afd8bfc0d57ba1283b0e957c935"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "82M"
tar_bytes = 85917184

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "32M"
zstd_bytes = 32537694

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220704"
previous_tag = "2022-07-04"
previous_file = "ruby-musl_arm64_2022-07-04_13-31-rootfs.tar.zst"
previous_sha256 = "d4cdb7465d7f899994718c42cb855c2dad2d2031285d3c5260bb877dce4cd31b"

current_version = "latest02"
current_date = "20220718"
old_file = "ruby-musl_arm64_2022-06-20_12-04-rootfs.tar.zst"
old_sha256 = "f469c4793d42689ae1111677f80d1aeebb57f2b4a1add07bdedd6c844417a915"
# edition 2021
# DISTRO_NAME=ruby_arm64
# ROOTFS_FILE=ruby-musl_arm64_2022-07-18_12-04-rootfs.tar.zst
# SHA256SUM=cf6072bf27cdf037229654fba25510976d600afd8bfc0d57ba1283b0e957c935
# BUILD_DATE=20220718
# BUILD_TAG=2022-07-18
# STATUS=completed
# VERSION=latest02
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-18
begin = 2022-07-18 12:02:36.174534146+00:00
start-sync_0 = 12:03:50
start-zstd = 12:03:56
start-sync_1 = 12:04:38
end-sync_1 = 12:04:45
end = 2022-07-18 12:04:45.586608230+00:00

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
ruby = 'ruby 3.1.2p20 (2022-04-12 revision 4491bb740a) [aarch64-linux-musl]'
gem = '3.3.7'
bundle = 'Bundler version 2.3.7'
```
