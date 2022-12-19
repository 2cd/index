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
tag = ["alpine", "2022-12-19", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ruby-musl_amd64_2022-12-19_12-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "9ffb3b8e9cbc30c0c05ddc16384ef64cf8a4ba16d976c8e8fecf0c53946427c0"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "87M"
tar_bytes = 90387456

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "34M"
zstd_bytes = 35266224

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221205"
previous_tag = "2022-12-05"
previous_file = "ruby-musl_amd64_2022-12-05_12-04-rootfs.tar.zst"
previous_sha256 = "8e9a2f8be29350e7e8d6247a3f8d9a35ec96917c5b5b19a35fa8eb8359c38307"

current_version = "latest01"
current_date = "20221219"
old_file = "ruby-musl_amd64_2022-11-21_12-04-rootfs.tar.zst"
old_sha256 = "a2f8bdba0cbb1b38ad82eaca42c0a85845041bb81c36c01aaa58a7b0d20cc0b9"
# edition 2021
# DISTRO_NAME=ruby_amd64
# ROOTFS_FILE=ruby-musl_amd64_2022-12-19_12-05-rootfs.tar.zst
# SHA256SUM=9ffb3b8e9cbc30c0c05ddc16384ef64cf8a4ba16d976c8e8fecf0c53946427c0
# BUILD_DATE=20221219
# BUILD_TAG=2022-12-19
# STATUS=completed
# VERSION=latest01
# END_TIME=12:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-19
begin = 2022-12-19 12:02:33.486463662+00:00
start-sync_0 = 12:04:08
start-zstd = 12:04:16
start-sync_1 = 12:04:54
end-sync_1 = 12:05:03
end = 2022-12-19 12:05:03.795543116+00:00

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
ruby = 'ruby 3.1.3p185 (2022-11-24 revision 1a6b16756e) [x86_64-linux-musl]'
gem = '3.3.26'
bundle = 'Bundler version 2.3.26'
```
