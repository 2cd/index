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
tag = ["alpine", "2023-09-11", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ruby-musl_arm64_2023-09-11_12-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "700b2b10e4cfb015a62cff937984fc0aab8f5311eb6d55fea433fd4821b1379f"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "102M"
tar_bytes = 106248192

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "36M"
zstd_bytes = 37511416

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230828"
previous_tag = "2023-08-28"
previous_file = "ruby-musl_arm64_2023-08-28_12-04-rootfs.tar.zst"
previous_sha256 = "033ad42d797ee8c54dcca7ac678b58a7924e25e5e1e5725a072b3932815edba7"

current_version = "latest02"
current_date = "20230911"
old_file = "ruby-musl_arm64_2023-07-31_12-05-rootfs.tar.zst"
old_sha256 = "ec3e1597bdf3757417aafcc9976993497c4cb2d45bf1efb285fa7166e773062a"
# edition 2021
# DISTRO_NAME=ruby_arm64
# ROOTFS_FILE=ruby-musl_arm64_2023-09-11_12-05-rootfs.tar.zst
# SHA256SUM=700b2b10e4cfb015a62cff937984fc0aab8f5311eb6d55fea433fd4821b1379f
# BUILD_DATE=20230911
# BUILD_TAG=2023-09-11
# STATUS=completed
# VERSION=latest02
# END_TIME=12:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-11
begin = 2023-09-11 12:02:41.243033885+00:00
start-sync_0 = 12:04:40
start-zstd = 12:04:47
start-sync_1 = 12:05:37
end-sync_1 = 12:05:45
end = 2023-09-11 12:05:45.591824106+00:00

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
