# ruby-arm64

## How to run it?

```sh
docker run \
    -it \
    --name ruby-arm64 \
    cake233/ruby-arm64
```

## How to exec shell?

```sh
docker exec -it ruby-arm64 bash
```

## ruby-arm64.toml

```toml
[main]
name = "ruby"
tag = ["latest", "2022-07-18"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ruby_arm64_2022-07-18_12-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a88ba25d5bba7bb3724c45f7edd8cb71f66fba746c5542323c3da46a45258b40"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "847M"
tar_bytes = 887812608

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "197M"
zstd_bytes = 206308167

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220704"
previous_tag = "2022-07-04"
previous_file = "ruby_arm64_2022-07-04_12-10-rootfs.tar.zst"
previous_sha256 = "acacda059c8d5798d9ae9ea1ef8450ed76e38bfcc8cd6e84f37b28d2f8cc8336"

current_version = "latest01"
current_date = "20220718"
old_file = "ruby_arm64_2022-06-20_12-11-rootfs.tar.zst"
old_sha256 = "e84bc4092d9f62abc343f5bd270eadc9256a70384689d8bd99d552ca8213f5b5"
# edition 2021
# DISTRO_NAME=ruby_arm64
# ROOTFS_FILE=ruby_arm64_2022-07-18_12-09-rootfs.tar.zst
# SHA256SUM=a88ba25d5bba7bb3724c45f7edd8cb71f66fba746c5542323c3da46a45258b40
# BUILD_DATE=20220718
# BUILD_TAG=2022-07-18
# STATUS=completed
# VERSION=latest01
# END_TIME=12:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-18
begin = 2022-07-18 12:02:30.453814597+00:00
start-sync_0 = 12:05:06
start-zstd = 12:05:21
start-sync_1 = 12:09:43
end-sync_1 = 12:09:59
end = 2022-07-18 12:09:59.285639494+00:00

[server]
repo = "cake233/ruby-arm64"

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
LANG = "en_US.UTF-8"
PATH = "/usr/local/bundle/bin${PATH:+:${PATH}}"
GEM_HOME = '/usr/local/bundle'
BUNDLE_SILENCE_ROOT_WARNING = '1'
BUNDLE_APP_CONFIG = '/usr/local/bundle'

[version]
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u3) 2.31'
ruby = 'ruby 3.1.2p20 (2022-04-12 revision 4491bb740a) [aarch64-linux]'
gem = '3.3.7'
bundle = 'Bundler version 2.3.7'
```
