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
tag = ["alpine", "2023-04-10", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ruby-musl_arm64_2023-04-10_12-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "260e38557af1897e82c334b7f2a4fbdac1c3f6b98f9d6f5ac76209cac0a8f860"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "102M"
tar_bytes = 105997824

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "36M"
zstd_bytes = 37428096

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230327"
previous_tag = "2023-03-27"
previous_file = "ruby-musl_arm64_2023-03-27_12-05-rootfs.tar.zst"
previous_sha256 = "97d6532376a47df1e9990bdf65b7d81358bb7dfbdbbe37f07213bd62e6a54b45"

current_version = "latest02"
current_date = "20230410"
old_file = "ruby-musl_arm64_2023-03-13_12-04-rootfs.tar.zst"
old_sha256 = "82a39eee07e51c53fd8ce2278bf22de27b248752e844162c2127537827016304"
# edition 2021
# DISTRO_NAME=ruby_arm64
# ROOTFS_FILE=ruby-musl_arm64_2023-04-10_12-05-rootfs.tar.zst
# SHA256SUM=260e38557af1897e82c334b7f2a4fbdac1c3f6b98f9d6f5ac76209cac0a8f860
# BUILD_DATE=20230410
# BUILD_TAG=2023-04-10
# STATUS=completed
# VERSION=latest02
# END_TIME=12:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-10
begin = 2023-04-10 12:02:35.776578896+00:00
start-sync_0 = 12:04:30
start-zstd = 12:04:42
start-sync_1 = 12:05:29
end-sync_1 = 12:05:40
end = 2023-04-10 12:05:40.931004135+00:00

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
ruby = 'ruby 3.2.2 (2023-03-30 revision e51014f9c0) [aarch64-linux-musl]'
gem = '3.4.10'
bundle = 'Bundler version 2.4.10'
```
