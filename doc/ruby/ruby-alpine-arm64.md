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
tag = ["alpine", "2023-05-22", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ruby-musl_arm64_2023-05-22_12-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c35e77bda5ad270ceeff6e4e93d6d57c61d0afe6e1327e1eb63c9f62b78c2539"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "102M"
tar_bytes = 106577920

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "36M"
zstd_bytes = 37497497

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230508"
previous_tag = "2023-05-08"
previous_file = "ruby-musl_arm64_2023-05-08_12-05-rootfs.tar.zst"
previous_sha256 = "64088b5ff7f1564b8d8516a8c41df97301c1edd1a94c21ae6661c2192b01ced1"

current_version = "latest01"
current_date = "20230522"
old_file = "ruby-musl_arm64_2023-04-24_12-05-rootfs.tar.zst"
old_sha256 = "1ac9819162d77d6bfb4e8b37ffa520507a90301df79c5a92c2fce86d29c8db8f"
# edition 2021
# DISTRO_NAME=ruby_arm64
# ROOTFS_FILE=ruby-musl_arm64_2023-05-22_12-05-rootfs.tar.zst
# SHA256SUM=c35e77bda5ad270ceeff6e4e93d6d57c61d0afe6e1327e1eb63c9f62b78c2539
# BUILD_DATE=20230522
# BUILD_TAG=2023-05-22
# STATUS=completed
# VERSION=latest01
# END_TIME=12:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-05-22
begin = 2023-05-22 12:02:37.546802965+00:00
start-sync_0 = 12:04:35
start-zstd = 12:04:41
start-sync_1 = 12:05:23
end-sync_1 = 12:05:29
end = 2023-05-22 12:05:29.787861107+00:00

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
ldd = 'musl libc (aarch64) Version 1.2.4'
ruby = 'ruby 3.2.2 (2023-03-30 revision e51014f9c0) [aarch64-linux-musl]'
gem = '3.4.10'
bundle = 'Bundler version 2.4.10'
```
