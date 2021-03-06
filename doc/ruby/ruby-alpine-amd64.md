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
tag = ["alpine", "2022-07-18", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ruby-musl_amd64_2022-07-18_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "856940809d381ebb3634035b7d22185ef37cf24b8468ea3037390dec64df2ac5"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "83M"
tar_bytes = 86340608

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "33M"
zstd_bytes = 33803159

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220704"
previous_tag = "2022-07-04"
previous_file = "ruby-musl_amd64_2022-07-04_13-30-rootfs.tar.zst"
previous_sha256 = "765cd26f421c91df20e7640b536a31708d7b5cda79b2982d895631531e463ccf"

current_version = "latest02"
current_date = "20220718"
old_file = "ruby-musl_amd64_2022-06-20_12-04-rootfs.tar.zst"
old_sha256 = "8a7fc974d4cfc047c1b1b925c212a283a03975892d2bb73b640d30a41080e41c"
# edition 2021
# DISTRO_NAME=ruby_amd64
# ROOTFS_FILE=ruby-musl_amd64_2022-07-18_12-04-rootfs.tar.zst
# SHA256SUM=856940809d381ebb3634035b7d22185ef37cf24b8468ea3037390dec64df2ac5
# BUILD_DATE=20220718
# BUILD_TAG=2022-07-18
# STATUS=completed
# VERSION=latest02
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-18
begin = 2022-07-18 12:02:31.013956421+00:00
start-sync_0 = 12:03:19
start-zstd = 12:03:26
start-sync_1 = 12:04:04
end-sync_1 = 12:04:11
end = 2022-07-18 12:04:11.499394736+00:00

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
