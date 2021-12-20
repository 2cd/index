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
tag = ["alpine", "2021-12-20", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "ruby-musl_arm64_2021-12-20_12-03.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "fce773463309a9bc78ade3a39d109f7e6fb8ca46403e91f853a400079b7a5b8a"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "75M"
tar_bytes = 77771776

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "31M"
zstd_bytes = 32044359

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211206"
previous_tag = "2021-12-06"
previous_file = "ruby-musl_arm64_2021-12-06_20-06-rootfs.tar.zst"
previous_sha256 = ""

current_version = "latest02"
current_date = "20211220"
old_file = "ruby-musl_arm64_2021-11-28_23-03-rootfs.tar.zst"
old_sha256 = ""
# edition 2021
# DISTRO_NAME=ruby_arm64
# ROOTFS_FILE=ruby-musl_arm64_2021-12-20_12-03-rootfs.tar.zst
# SHA256SUM=fce773463309a9bc78ade3a39d109f7e6fb8ca46403e91f853a400079b7a5b8a
# BUILD_DATE=20211220
# BUILD_TAG=2021-12-20
# STATUS=completed
# VERSION=latest02
# END_TIME=12:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-20
begin = 2021-12-20 12:02:31.720839154+00:00
start-sync_0 = 12:03:21
start-zstd = 12:03:31
start-sync_1 = 12:03:42
end-sync_1 = 12:03:51
end = 2021-12-20 12:03:51.196748163+00:00

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
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
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
ldd = 'musl libc (aarch64) Version 1.2.2'
ruby = 'ruby 3.0.3p157 (2021-11-24 revision 3fb7d2cadc) [aarch64-linux-musl]'
gem = '3.2.32'
bundle = 'Bundler version 2.2.32'
```
