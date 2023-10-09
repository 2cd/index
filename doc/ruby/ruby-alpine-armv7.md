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
tag = ["alpine", "2023-10-09", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ruby-musl_armhf_2023-10-09_12-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "007eb2ea5e8ca323514d3146b9a49c50295823f5adddb7b883bd018eeafce38b"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "74M"
tar_bytes = 77001728

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "33M"
zstd_bytes = 33839104

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230925"
previous_tag = "2023-09-25"
previous_file = "ruby-musl_armhf_2023-09-25_12-05-rootfs.tar.zst"
previous_sha256 = "66632b377002c0f30611ca602e30356eeb94137f328844ce75e8474bd6a8e61e"

current_version = "latest02"
current_date = "20231009"
old_file = "ruby-musl_armhf_2023-09-11_12-04-rootfs.tar.zst"
old_sha256 = "fb38cf547dcb9ac234a51876b19bbbf2daf533997ef6ca6d940f6c8decab6992"
# edition 2021
# DISTRO_NAME=ruby_armhf
# ROOTFS_FILE=ruby-musl_armhf_2023-10-09_12-05-rootfs.tar.zst
# SHA256SUM=007eb2ea5e8ca323514d3146b9a49c50295823f5adddb7b883bd018eeafce38b
# BUILD_DATE=20231009
# BUILD_TAG=2023-10-09
# STATUS=completed
# VERSION=latest02
# END_TIME=12:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-09
begin = 2023-10-09 12:02:37.681914936+00:00
start-sync_0 = 12:04:11
start-zstd = 12:04:23
start-sync_1 = 12:04:58
end-sync_1 = 12:05:06
end = 2023-10-09 12:05:06.399180801+00:00

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
ldd = 'musl libc (armhf) Version 1.2.4'
ruby = 'ruby 3.2.2 (2023-03-30 revision e51014f9c0) [arm-linux-musleabihf]'
gem = '3.4.10'
bundle = 'Bundler version 2.4.10'
```
