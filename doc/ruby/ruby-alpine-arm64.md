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
tag = ["alpine", "2022-10-10", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ruby-musl_arm64_2022-10-10_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "25497232b8ab487becb0a4262413c7b3e870d6cbf139ffe3cc7bfb3d3674a2e4"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "82M"
tar_bytes = 85901312

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "32M"
zstd_bytes = 32543947

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220926"
previous_tag = "2022-09-26"
previous_file = "ruby-musl_arm64_2022-09-26_12-04-rootfs.tar.zst"
previous_sha256 = "1df63832a1047c41f380f131f92048cea122eba0ba2246d263376badfc741cc2"

current_version = "latest02"
current_date = "20221010"
old_file = "ruby-musl_arm64_2022-09-12_12-04-rootfs.tar.zst"
old_sha256 = "78bf17cc28e2583a62219b588680a47f5c91558e3370bf437dac82ec5ea8d6f1"
# edition 2021
# DISTRO_NAME=ruby_arm64
# ROOTFS_FILE=ruby-musl_arm64_2022-10-10_12-04-rootfs.tar.zst
# SHA256SUM=25497232b8ab487becb0a4262413c7b3e870d6cbf139ffe3cc7bfb3d3674a2e4
# BUILD_DATE=20221010
# BUILD_TAG=2022-10-10
# STATUS=completed
# VERSION=latest02
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-10
begin = 2022-10-10 12:02:27.740582533+00:00
start-sync_0 = 12:03:30
start-zstd = 12:03:36
start-sync_1 = 12:04:17
end-sync_1 = 12:04:24
end = 2022-10-10 12:04:24.282912750+00:00

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
