# ruby-alpine-armv7

## How to run it?

```sh
docker run \
    -it \
    --name ruby-alpine-armv7 \
    cake233/ruby-alpine-armv7
```

## How to exec shell?

```sh
docker exec -it ruby-alpine-armv7 bash
```

## ruby-alpine-armv7.toml

```toml
[main]
name = "ruby"
tag = ["alpine", "2022-04-11", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false
syntax_version = "0.0.0-alpha.3"

[file]
name = "ruby-musl_armhf_2022-04-11_11-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "4578ceca8d565bfb834ccdb4588d6ae0b5dd1b7f7f12112e08219b8f26a55c1d"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "72M"
tar_bytes = 75289088

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "31M"
zstd_bytes = 31701344

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220328"
previous_tag = "2022-03-28"
previous_file = "ruby-musl_armhf_2022-03-28_11-04-rootfs.tar.zst"
previous_sha256 = "397760fa944e998b3ce4ad7ad65731b60c902cae5a480513d9faafe99c6592b3"

current_version = "latest02"
current_date = "20220411"
old_file = "ruby-musl_armhf_2022-03-24_12-28-rootfs.tar.zst"
old_sha256 = "1e36365560986770955608e98a1dd5e8adaf74dbd4e6d8c0fa6667b5ca18a387"
# edition 2021
# DISTRO_NAME=ruby_armhf
# ROOTFS_FILE=ruby-musl_armhf_2022-04-11_11-04-rootfs.tar.zst
# SHA256SUM=4578ceca8d565bfb834ccdb4588d6ae0b5dd1b7f7f12112e08219b8f26a55c1d
# BUILD_DATE=20220411
# BUILD_TAG=2022-04-11
# STATUS=completed
# VERSION=latest02
# END_TIME=11:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-11
begin = 2022-04-11 11:02:36.791602880+00:00
start-sync_0 = 11:03:42
start-zstd = 11:03:48
start-sync_1 = 11:04:23
end-sync_1 = 11:04:30
end = 2022-04-11 11:04:30.708109302+00:00

[server]
repo = "cake233/ruby-alpine-armv7"

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
ldd = 'musl libc (armhf) Version 1.2.2'
ruby = 'ruby 3.1.1p18 (2022-02-18 revision 53f5fc4236) [arm-linux-musleabihf]'
gem = '3.3.7'
bundle = 'Bundler version 2.3.7'
```
